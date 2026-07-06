# suportProjekt

This project is a TwinCAT XPlanar support project for controlling one mover through a simple test sequence.

The program starts with system initialization. After the project is initialized, the mover can be enabled, started, moved around a defined track, soft stopped at the leave area, disabled, removed from the active area, and later added back in again.

## How To Run The Mover

1. Initialize the XPlanar environment.
2. Set the `mEnable` boolean to enable the mover.
3. Set the `mStart` boolean to start the movement sequence.
4. The mover follows the predefined path and rotates as part of the track.
5. When the mover reaches the leave area, press `softStop` to stop the sequence safely.
6. Set the `mDisable` boolean to disable the mover.
7. Call `tryLeavingMovementArea` to remove the mover from the movement area.
8. Put the mover back on the area.
9. Call `tryEnteringMovementArea` to place the mover back into the movement area.
10. Set `mEnable` again.
11. Set `mStart` again and the mover will follow the path again.

## Main Controls

The `MAIN` program contains the main control flags for the test sequence:

- `mEnable` - enable the mover
- `mStart` - start the movement cycle
- `mStop` - stop the mover
- `softStop` - stop the current cycle safely at the leave area
- `mDisable` - disable the mover
- `mReset` - reset the control logic
- `tryLeavingMovementArea` - remove the mover from the active area
- `tryEnteringMovementArea` - add the mover back into the active area

## Movement Sequence

After startup, the mover follows a predefined path using several target positions and one rotation move. The current logic is intended for testing one mover only, so the sequence is kept simple and repeatable.

## Entering And Leaving The Movement Area

The project also includes two helper actions:

- `LeavingMovementArea` sets the movement area to `0`, which removes the mover from the active area.
- `EnterMovementArea` assigns a movement area OID again so the mover can re-enter the active area.

This makes the project useful for experimenting with mover lifecycle control in a controlled XPlanar setup.
