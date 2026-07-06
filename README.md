# XPlanar Experiments

This repository contains early-stage experiments with the Beckhoff **XPlanar** system.  
The purpose is to investigate how movers can be coordinated, inserted, removed, grouped, and controlled under different dynamic operating conditions [file:1].

## Purpose

The project is used to explore and document practical and research-oriented XPlanar behaviors, with an initial focus on:

- Single mover enter/leave while other movers continue operation [file:1]
- Multiple movers entering/leaving at the same time [file:1]
- Pair formation and dynamic pair reconfiguration [file:1]

The repository acts as both a technical playground and a documentation base for structured experimentation [file:1].

## Librarys for twin cat
- XPlanar Utility Library
- TF5430 | TwinCAT 3 Planar Motion
- TF5890 |TwinCAT 3 Xplanar

## Initial Research Focus

The first phase of this repository investigates the following questions:

- Can a single mover be removed from and reintroduced into a running system without critically disturbing other movers? [file:1]
- How does the system behave when several movers enter or leave simultaneously? [file:1]
- Can movers be organized into pairs and reconfigured dynamically during operation? [file:1]

These experiments are intended to clarify functional behavior, control constraints, and possible design patterns for future XPlanar applications [file:1].

## Planned Experiments

### 1. Single mover enter/leave

This experiment investigates how the system handles one mover being taken out of operation and later reintroduced while other movers continue their normal cycle [file:1].

Focus areas:

- Stability of the remaining movers
- Recovery after re-entry
- Need for safe zones or gate logic
- Repeatability over multiple cycles

### 2. Multi enter/leave

This experiment investigates whether multiple movers can enter and leave the system at the same time without creating synchronization or stability problems [file:1].

Focus areas:

- Simultaneous state changes
- Coordination and sequencing logic
- Alarm 
