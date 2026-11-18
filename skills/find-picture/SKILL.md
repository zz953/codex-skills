---
name: find-picture
description: Search a local photo collection for a reference subject or event participant, recover overlooked photos from group shots and adjacent frames, verify candidates, and copy requested originals. Use for photo folders, reference images, race bib numbers, and follow-up searches after user feedback.
---

# Find Picture

## 1. Inventory the collection and record reference clues

- Identify the source folders, which subfolders are in scope, confirmed matches, examples the user ruled out, and the output directory. Track files by relative path so identical names from different cameras or folders stay distinct. Before a follow-up search, check what the user has added, moved, or confirmed.
- Collect clues from confirmed photos. Keep the team number and leading zeros when recording bibs. Track changes in clothing and gear by date and scene. Use the area circled by the user to locate the subject. People nearby and background details can help match scenes.
- Index photos by original EXIF capture time, camera, and file sequence. When clocks differ, sequence numbers skip, or EXIF is missing, compare neighboring frames and recurring scenes. Record any fallback timestamps and use time and sequence proximity to narrow the search.

## 2. Scan and review candidates

- Test decoding, orientation, and bib recognition on a sample before running across the collection. [RapidOCR](https://github.com/RapidAI/RapidOCR) can run locally. Record processed paths, results, and failures so the scan can resume in batches. Projects such as [RunnerBibTagger](https://github.com/chbornman/RunnerBibTagger) illustrate bib detection. For tools that write image metadata, use a read-only workflow or work on copies.
- Preserve the raw OCR text, bounding boxes, and confidence scores. For bibs printed on two lines, check that both lines come from the same bib region. Allow for common OCR errors when collecting candidates, then verify the text against the original image. Different teams may use the same participant number.
- Start with frames before and after confirmed matches, other cameras covering the same scene, and nearby shooting locations. Use changes in scene and gaps in capture time to decide when to broaden the search. When the user supplies an annotated screenshot, [OpenCV feature matching](https://github.com/opencv/opencv/blob/5.x/doc/tutorials/features/feature_flann_matcher/feature_flann_matcher.markdown) can help locate the area in the original or a similar view. Check the projected location against the original.
- For group photos, distant subjects, and obscured bibs, use thumbnails to locate promising areas, then inspect overlapping crops at the original resolution. Compare backpack design, jackets, gaiters, and other distinctive gear from the same period. Check the subject's position, nearby teammates, and continuity across frames. Clothing color, teammates, and background details can surface candidates for review. Where appropriate, use local face similarity to prioritize candidates, then review visible evidence or user feedback.
- Add newly confirmed photos to the references and follow any new leads in capture time, camera angle, or gear. Remove examples the user ruled out from the matching references. Track whether the user ruled out one person in a photo or the entire photo.

## 3. Copy originals and verify coverage

- Record the original path, the evidence supporting each result, and its review status. Copy the original files to the requested destination. If a name already exists, compare file contents. Skip identical copies and give different files distinct names. Verify each copy against the source. Move originals or write their metadata only when requested.
- Compare the inventory against automated scans, manual reviews, previously confirmed photos, processing failures, and unreviewed files. Report the number of new results and where they were saved. Indicate which candidates still need confirmation. Report a full manual review only if every photo was reviewed individually. A full automated scan can still miss matches.
