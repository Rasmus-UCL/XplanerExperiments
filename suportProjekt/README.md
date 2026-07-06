# suportProjekt

This project is a TwinCAT XPlanar support project for controlling one mover through a simple test sequence.

The program starts with system initialization. After the project is initialized, the mover can be enabled, moved through a fixed path, soft stopped, disabled, and then moved out of or back into the movement area.

## Project flow

1. Initialize the XPlanar environment.
2. Enable the mover.
3. Start the movement sequence.
4. Move the mover through the programmed positions.
5. Soft stop the mover when needed.
6. Disable the mover.
7. Remove the mover from the movement area.
8. Add the mover back into the movement area.

## Main controls

The `MAIN` program contains the main control flags for the test sequence:

- `mEnable` - enable the mover
- `mStart` - start the movement cycle
- `mStop` - stop the mover
- `softStop` - end the current cycle safely
- `mDisable` - disable the mover
- `mReset` - reset the control logic
- `tryLeavingMovementArea` - remove the mover from the active area
- `tryEnteringMovementArea` - add the mover back into the active area

## Movement sequence

After startup, the mover follows a predefined path using several target positions and one rotation move. The current logic is intended for testing one mover only, so the sequence is kept simple and repeatable.

## Entering and leaving the movement area

The project also includes two helper actions:

- `LeavingMovementArea` sets the movement area to `0`, which removes the mover from the active area.
- `EnterMovementArea` assigns a movement area OID again so the mover can re-enter the active area.

This makes the project useful for experimenting with mover lifecycle control in a controlled XPlanar setup.
