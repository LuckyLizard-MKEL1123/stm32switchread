# Milestone2.1.2: stm32switchread
Group Name: **Lucky Lizard** :lizard:

Group Member: 
1. **Andi Nur Asyikin Binti Andi Zainuddin**
2. **Lim Yong Chuan**
3. **Nur Fatini Binti Isa**

## Ojective
Interface simple devices GPIO ports
## Equipment
- [x] Board used: **NUCLEO-F411RE**
- [x] Software used: **STM32CubeIDE**
- [x] Breadboard
- [x] LEDs
- [x] Jumper
- [x] DIP switch
- [x] Push button (on nucleo board)

## Procedure
1. In this milestone, the speed of knight rider lights are determined by the DIP switch value only when the push button is pressed.
2. The source code from milestone 2.1.1 is modified with additional function of DIP switch and push button: [stm32knightrider.c](https://github.com/LuckyLizard-MKEL1123/stm32knightrider/blob/main/stm32knightrider.c)
3. The input data registers, GPIOA_IDR are used to read in input data from push button and DIP switch.
4. The push button of  nucleo board is assigned by port C 13.
5. An if condition is used inside the for loop to so that the DIP switch can only be read in if the push button is set.
6. As for the 4-bit DIP switch, GPIOB[3:0] of nucleo board is used.
7. The speed should be as shown below:

| DIP switch[0:3] | Interval between LEDs [ms] | Time taken from first to last LED [ms] |
|-----------------|-----------------------|-----------------------------------|
| 0000 | 1000 | 8000 |
| : | : | : |
| 1111 | 125 | 1000 |

8. A *count_delay* function is written to calculate the delay for each input value read in by the DIP switch.
9. The formula used to count the delay is as shown below.

| Graph | Reference formula | Implementation |
|-------|-------------------|----------------|
| ![y = mx + c](https://github.com/LuckyLizard-MKEL1123/stm32switchread/blob/main/Capture.PNG) | y = mx + c | delay = - 58.3 * swdata + 1000 ; where, swdata is DIP input |

## Results
Link for milestone 2.1.2 demo: [read_switch](https://youtu.be/Xv-8sHphlcM)
## References
1. https://www.youtube.com/watch?v=KFSpxY_KM5A
