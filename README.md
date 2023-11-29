# LethalAPI.GameLibs

[![Build](https://github.com/dhkatz/LethalAPI.GameLibs/actions/workflows/build.yml/badge.svg)](https://github.com/dhkatz/LethalAPI.GameLibs/actions/workflows/build.yml)
![Nuget](https://img.shields.io/nuget/v/LethalAPI.GameLibs)

Creates stripped and publicized game libraries for Lethal Company.

If the game gets updated, this package needs to get updated too.

## Introduction

`strip-assembiles.bat` does two things:

- Strips game assembiles using [NStrip](https://github.com/BepInEx/NStrip). This removes game code and leaves only API definitions.
- Publicizes `Assembly.CSharp.dll` and `AAssembly-CSharp-firstpass.dll`. This makes all types, methods, properties and fields public, to make modding easier.

## Usage

### Generating Modified Assemblies

- Make sure you start off with a clean version of the game files, with no extra/modified dlls.
- Drag the game's exe and drop it on `strip-assembiles.bat`.
- Dlls are stripped, publicized, and placed in `package\lib`.

### Publicized Assemblies

By default, only `Assembly-CSharp.dll` and `Assembly-CSharp-firstpass.dll` are publicized. All other dlls are stripped only. To publicize other dlls, edit `strip-assemblies.bat` and add the dll names to the `toPublicize` variable.

### Untouched Assemblies

By default, every game assembly gets stripped. If there's any assembly you wish to keep in the package in their original state, add the dll names to the `dontTouch` variable.
