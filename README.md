# piHPSDR

piHPSDR is a Open Source hamradio SDR application for Linux and macOS, primarily for use with SDR using the HPSDR protocol 1 & 2 and was initially developed by John Melton G0ORX/N6LYT.

Lately Christoph/DL1YCF has continued the development of piHPSDR and add a lot of options, which hasn't include the original version, so DL1YCF's version is the most up-to-date version of piHPSDR. You can find his version here:

[https://github.com/dl1ycf/pihpsdr/](https://https://github.com/dl1ycf/pihpsdr/)

## My "improved" version of piHPSDR

The original version is made for running with Linux Desktops, Macs with macOS, but for Raspberry Pi 3/4/5 too and can be used with low-resolution Displays or Monitors too, start from 640x480 screen size.

My version breaks the limitation of low-resolution screens and **is made for screen sizes higher than 1280 x 800 or more** and has the focus of macOS and Linux Desktops.

**IMPORTANT: If you want to use piHPSDR with small displays, you need to use Christoph's/DL1YCF version !**

I call my version not as a "fork" of DL1YCF's version, it's more a improved version. As far as possible my version is ever merged to the most actual code base of DL1YCF's version, but with my additional improvements.

## Changes in my version against the version of DL1YCF

1. change the work-directory from

```
   ˜/Library/Application Support/piHPSDR (macOS)
   ˜/.config/pihpsdr (Linux)
```

to

```
   ˜/Library/Application Support/piHPSDR-desktop (macOS)
   ˜/.config/pihpsdr-desktop (Linux)
```

So we have a different work-directory for my improved version of piHPSDR, which not affected the original work-directory.

2. In the TX menu I removed the option **Digi-drive** and replace it with the option **Leveler gain** and **Leveler switch on/off**.
3. I made some helpful GUI improvements, e.g. I extend the digital S-Meter, show state and level of CFC, Leveler, processor (which is the baseband compressor).
4. For activate my additional improvements I add a new option in the **Makefile** called **DESKTOP=ON**, which add a new compiler directive __LDESK__ . That means "large desktop". In my code base all improvements are implemented with

```
#if defined (__LDESK__)
  (improvement code)
#else
  (original code)
#endif
```

So the original code is still present inside and will be **not removed**.

5. Remove the manual part from my code base, please use the manual from the version of DL1YCF instead. I have no plans and no time for a own manual, sri.

## Requirements - personal skills and technical knowledge

**I only publish pure source code, not ready-compiled binaries**. That means, you need to compile the application by yourself and install it. Follow the instructions *Appendix J: LINUX compile from sources* and *Appendix K: MacOS compile from sources* which you can read in the piHPSDR [manual at DL1YCF pihpsdr Github repository](https://github.com/dl1ycf/pihpsdr/releases/download/current/piHPSDR-Manual.pdf).

I do not teach a basic course in using operating systems too ! **You** need to know, how you use a shell in Linux or macOS, a compiler and so on. Without this knowledge you will surely don't have success, if you don't know, what and how you need to do all. With macOS you need to install the Homebrew-Environment and XQuartz for running piHPSDR.