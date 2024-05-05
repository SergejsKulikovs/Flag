#include "mbed.h"

InterruptIn button(USER_BUTTON);
volatile bool buttonPressed = false;

void onButtonPress() {
    buttonPressed = true;
}

int main() {
    while (true) {
        if (buttonPressed) {
            printf("Button pressed\n");
            buttonPressed = false;
        }
        ThisThread::sleep_for(100ms);
    }
}
