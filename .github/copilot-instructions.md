# GitHub Copilot Instructions

## Overview
This repository contains the 2026 Robot Code for FRC Team 6238. It uses WPILib Command-based Java and AdvantageKit for logging and replay. The project includes subsystems for drive, vision, shooter, hopper, intake, and superstructure, as well as autonomous and teleop navigation features.

## Key Commands
- **Build the project:**
  ```bash
  ./gradlew build
  ```
- **Run tests:**
  ```bash
  ./gradlew test
  ```
- **Deploy to the robot:**
  ```bash
  ./gradlew deploy
  ```
- **Replay AdvantageKit logs:**
  ```bash
  ./gradlew replayWatch
  ```
- **Apply formatting:**
  ```bash
  ./gradlew spotlessApply
  ```

## Project Structure
- **src/main/java:** Contains the main robot code, including subsystems and commands.
- **src/test/java:** Contains unit tests for subsystems and commands.
- **vendordeps:** JSON files for external dependencies like WPILib, AdvantageKit, and Phoenix libraries.
- **hoppermodel:** Python-based object detection code for the Jetson Nano.

## Development Guidelines
1. **Follow the AdvantageKit IO Layer Pattern:**
   - Define an `IO` interface with `@AutoLog` inputs.
   - Implement hardware-specific and simulation-specific `IO` classes.
   - Use the subsystem to manage `IO` inputs and log data.
2. **Use Spotless for Formatting:**
   - Formatting is enforced automatically before compilation.
   - Run `./gradlew spotlessApply` to fix formatting issues.
3. **Write Unit Tests:**
   - Mock `IO` interfaces and use `doAnswer` to simulate hardware behavior.
   - Ensure all `*Connected` flags are set to `true` in tests.

## Example Prompts
- "Generate a command to align the robot to a target using the drive subsystem."
- "Write a unit test for the shooter subsystem to verify flywheel speed control."
- "Add a new AdvantageKit log replay command to the build script."

## Notes
- Refer to [CLAUDE.md](../CLAUDE.md) for detailed architecture and testing patterns.
- For Jetson Nano setup, see [SETUP_JETSON.md](https://github.com/6238/2026-Robot/blob/main/SETUP_JETSON.md).
- The object detection structure diagram is available in the [README.md](../README.md).