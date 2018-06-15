# iOS Development Thoughts

This page documents my various thoughts and items to remember when developing for iOS.

## Simulator Tricks

I hate start up Xcode just to start up a simulator. This is especially painful when preparing CI machines.

### Starting a Simulator

Below are two commands that help make listing and starting simulators a breeze.

First, run `xcrun simctl list` from the terminal. This command produces the following:

```bash
mbpro:~ user$ xcrun simctl list
== Device Types ==
iPhone 4s (com.apple.CoreSimulator.SimDeviceType.iPhone-4s)
...
iPad Pro (12.9-inch) (com.apple.CoreSimulator.SimDeviceType.iPad-Pro)
...
Apple Watch Series 2 - 38mm (com.apple.CoreSimulator.SimDeviceType.Apple-Watch-Series-2-38mm)
...
== Runtimes ==
iOS 11.3 (11.3 - 15E217) - com.apple.CoreSimulator.SimRuntime.iOS-11-3
iOS 11.4 (11.4 - 15F79) - com.apple.CoreSimulator.SimRuntime.iOS-11-4
...
== Devices ==
-- iOS 11.3 --
    iPhone 5s (7744E450-C895-439B-9CF5-C42CF5D8457C) (Shutdown)
    iPhone 6 (05B56AC1-BD88-4FAC-ADE3-F2043809602A) (Shutdown)
    iPhone 6 Plus (4BA7C5B3-56D7-4723-8376-0D2DAECCF8F9) (Shutdown)
...
```

Find and copy the ID of the type of simulator you want. I chose the iPhone 6, which has a UDID of `05B56AC1-BD88-4FAC-ADE3-F2043809602A`.

Now, run the following command with the UDID you just copied. Simulator is the name of the app you want to start.

```bash
mbpro:~ user$ open -a "Simulator" --args -CurrentDeviceUDID 05B56AC1-BD88-4FAC-ADE3-F2043809602A
```

### Stopping a Simulator

Use the following commands to kill all instances of the simulator. This includes killing the Simulator Service (if you're using CI, use this command cautiously. It can be helpful since some CI tools run the simulator headless).

```bash
mbpro:~ user$ killall -9 "iPhone Simulator" || true killall -9 "iOS Simulator" || true killall -9 "Simulator" || true killall -9 "com.apple.CoreSimulator.CoreSimulatorService" || true
```

## App Code vs Xcode

Xcode is great. Until you start using App Code and realize that being a first class citizen is possible! While you can't edit nibs or storyboards through App Code, the rest of your experience developing and refactoring code is greatly enhanced. Especially when you realize you can finally customize your code formatting rules! My current thoughts are that you should use them beside each other, each to their own strength.
