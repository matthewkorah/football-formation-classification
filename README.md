## Overview

This project automatically classifies offensive football formations from pre-snap broadcast images using computer vision. Casual viewers often struggle to recognize and understand common offensive formations during live games or highlight replays, which can make following strategy difficult. By identifying formations such as trips, bunch, or balanced sets, this system provides an accessible way to interpret offensive structure without requiring expert football knowledge.

## Intended Use

The intended users are casual football fans and viewers who lack formal knowledge of offensive formations. The system could be used during live broadcasts, highlight replays, or film breakdowns to automatically label offensive formations before the snap. This helps viewers better understand offensive strategy in real time, improving engagement and lowering the learning barrier for newer fans.

## Data Collection and Preparation

The dataset was collected from eight NFL games from the 2024 season by manually extracting pre-snap broadcast images of offensive formations. Each image was carefully curated through several preprocessing steps, including cropping out irrelevant regions such as the crowd, normalizing play direction so the offense always moves in the same direction, straightening camera tilt, and converting images to grayscale to prevent reliance on team colors. Images were then manually labeled by studying offensive layouts and cross-referencing broadcast commentary to ensure label accuracy.

## Model and Evaluation

The model is evaluated using classification accuracy and confusion matrices on held-out validation and test sets. This project required significant manual effort and domain research, particularly in defining a consistent formation taxonomy and reducing visual noise in broadcast footage. A key limitation identified during development is variation in camera angles across games. While geometric field alignment techniques similar to face alignment could improve performance, implementing such normalization was beyond the scope of this project due to inconsistent broadcast perspectives.

## Formation Labels

We define six general offensive formation labels based on quarterback alignment and receiver structure:

- **balanced**  
  A shotgun formation with receivers relatively evenly distributed across both sides of the field.

- **trips**  
  A shotgun formation with three receivers aligned on one side of the formation.

- **bunch**  
  A shotgun formation where receivers are tightly clustered together in a compact, triangle-like alignment.

- **tight**  
  A shotgun formation with compact spacing that is neither spread nor clustered into a bunch.

- **uc_balanced**  
  An under-center formation with traditional, balanced receiver spacing.

- **uc_heavy**  
  An under-center formation with condensed spacing, typically used in short-yardage situations with extra blockers near the line of scrimmage.
