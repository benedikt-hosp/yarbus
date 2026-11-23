# Yarbus

Open, vendor-independent analysis of eye-tracking data. Local, reproducible, with areas of interest in 360° video and VR.

> **Status:** planning. There is no code yet. This repository holds the plan, the data format and the roadmap. Development starts in June 2027.

## Why

Eye-tracking data is biometric: it reveals what people attend to, how tired they are and even hints about their health. Yet most research labs analyse it in closed software from device vendors or in cloud services. Licences are expensive, every vendor has its own format, and the computations behind the results are not open. Studies are hard to reproduce, and sensitive data often leaves the lab where participants gave their consent.

Yarbus is meant to be the free alternative: a tool that researchers can understand, check and adapt, that runs on their own machines and that makes every analysis step reproducible.

The name honours Alfred L. Yarbus, whose work in the 1960s showed how the task shapes where we look.

## Planned features

- **Importers** for common devices and open recording software: Pupil Labs, Tobii, VR recordings from Unity, OpenIris.
- **One open data format** for all imported data, based on Eye-Tracking-BIDS.
- **Fixation and saccade detection** with documented methods; all parameters are stored with the result.
- **Areas of interest** on images, videos, 360° videos and in VR scenes, tracked from frame to frame with open segmentation models that run locally.
- **Group comparisons** with effect sizes and confidence intervals.
- **Methods text** generated from fixed templates (no language model), ready to cite.
- **Reproducible analysis runs:** data version, software version, parameters and results in one package, publishable with a DOI via Zenodo (DataCite metadata), following the FAIR principles.
- **Local web interface** that works offline, on a laptop or a lab server. Everything is also scriptable.

## Roadmap (June to November 2027)

1. **June:** talks with five labs about their workflows, data format, first three importers.
2. **July to August:** fixation and saccade detection, AOI editor for images, video, 360° and VR.
3. **September:** group statistics, methods text, version 0.1 for test labs.
4. **October:** tests in the labs with their own data, fixes, tutorials with open example data.
5. **November:** version 0.5 with documentation and publishing of analysis runs with DOI, workshop for researchers.

## Data format

Draft, to be refined with the test labs:

```
dataset/
  dataset_description.json
  participants.tsv            # pseudonymised IDs only
  sub-<id>/
    ses-<id>/
      eyetrack/
        sub-<id>_ses-<id>_task-<task>_eyetrack.tsv.gz   # gaze samples
        sub-<id>_ses-<id>_task-<task>_eyetrack.json     # device, rate, units, calibration
        sub-<id>_ses-<id>_task-<task>_events.tsv        # trials, stimuli
  stimuli/
  derivatives/yarbus/        # fixations, AOI hits, statistics, run log
```

## Licence and contributions

Yarbus is licensed under the **GNU Affero General Public License v3.0** (see `LICENSE`).

Contributions are welcome once development starts. Contributors will be asked to sign a contributor licence agreement (CLA), so that the project can be maintained and relicensed if needed. Details will follow in `CONTRIBUTING.md`.

## Contact

Benedikt Hosp · info@bwhosp.science
