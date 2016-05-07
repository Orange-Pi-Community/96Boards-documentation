# Examples - Sample Code

## Contents

- [GPIO Examples](#gpio-examples)
- [I2C Examples](#i2c-examples)
- [SPI Examples](#spi-examples)

***

## GPIO Examples

### Example #1 - Through the shell

This is the first and simplest example one could execute on a 96Boards. For this example you will access and manipulate the GPIOs via command line using the built in terminal application on your 96Boards. For this example you WILL NOT need any particular library, however, low-speed expansion header pins/GPIOs naming conventions can be significantly simplified by installing the **libsoc** library beforehand.

**It is important to note:** Each 96Boards varies in the sense it uses a different [System on Chip (SoC)](). These SoCs have different GPIO values for which we can access. The nameing convention included in the [96Boards Specification]() allows us use the **libsoc** library to path the different GPIO values (regardless of the 96Boards you are using) to its pin location and/or the letter it is assigned. For instance:

| Actual pin | Nameing convention #1 | Nameing convention #2 |
|:----------:|:---------------------:|:---------------------:|
|   Pin 23   |        GPIO_A         |        GPIO_23        |
|   Pin 24   |        GPIO_B         |        GPIO_24        |
|   Pin 25   |        GPIO_C         |        GPIO_25        |
|   Pin 26   |        GPIO_D         |        GPIO_26        |
|   Pin 27   |        GPIO_E         |        GPIO_27        |
|   Pin 28   |        GPIO_F         |        GPIO_28        |
|   Pin 29   |        GPIO_G         |        GPIO_29        |
|   Pin 30   |        GPIO_H         |        GPIO_30        |
|   Pin 31   |        GPIO_I         |        GPIO_31        |
|   Pin 32   |        GPIO_J         |        GPIO_32        |
|   Pin 33   |        GPIO_K         |        GPIO_33        |
|   Pin 34   |        GPIO_L         |        GPIO_34        |

This example instruction set will assume you have installed the **libsoc** library and thus should have the paths to our nameing conventions set in your 96Boards.

To access the GPIOs through the Linux shell, open the terminal (start menu > other > LXTerminal; right click this to add shortcut to your desktop if you desire) and give yourself super user access:

```shell
$ sudo su
```

Giving yourself superuser access will allow you to modify the GPIOs (if you get an access denied for a GPIO, this means you’re trying to modify a GPIO the board is using for itself)

Once you have superuser access, navigate to the gpio folder with the following command:

```shell
# cd /sys/class/gpio 
```

From within the GPIO folder there are several naming conventions(mentioned above) which can be used to manipulate each function of the GPIO itself.


This will give us the ability to work with a certain GPIO pin
```shell
# echo $[GPIO_#/Letter] > export
```

This returns the direction of the GPIO
```shell
# cat direction
```

Sets direction of GPIO
```shell
# echo [out or in] > direction
```

This returns 0 if the pin is off, 1 if the pin is on
```shell
# cat value
```

Sets value of GPIO
```shell
# echo [0 or 1] > value
```

Using a multimeter set to measuring voltage, you can probe the pin you are toggleing along with one of the ground nodes (Pins 1,2,39, and 40), to watch the voltage switch between ~1.8V and 0V.

### Example #2 - Triple library LED push button

This repository, created by Linaro's David Mandala, demonstrates the use of three different libraries using three different scripts. Instructions on how to compile and execute the code can be found in the README.md file which is included in the repository download. Simply clone the repoistory onto your 96Boards and follow README.md instructions.

These examples were made using the [Linker mezzanine card starter kit](../../../MezzanineProducts/Linker%20mezzanine%20card%20starter%20kit/README.md) made by [Arrow](http://www.arrow.com)

**Commands:**

```shell
$ git clone https://github.com/dmandala/library_test.git<Enter>
$ cd library_test<Enter>
$ cat README.md<Enter>
```

### Example #3 - Sensor, sensors, and more sensors

This public instruction set was created by Barry Byford, a DragonBoard 410c enthusiast from the UK. The code provided for these examples are simple and still being developed. Instructions for setting up the libsoc_zero library can be found on his website along side his sample code and examples.

These examples were made using the [Linker mezzanine card starter kit](../../../MezzanineProducts/Linker%20mezzanine%20card%20starter%20kit/README.md) made by [Arrow](http://www.arrow.com)

http://pythonhosted.org/libsoc_zero/index.html

***

## I2C Examples

Coming Soon...

***

## SPI Examples

Coming Soon...