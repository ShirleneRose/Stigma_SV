# Stigma Classification in Sexual Violence Discourse on Reddit

## Overview

This research examines how stigma related to sexual violence is expressed in posts and support is expressed in comments on Reddit. Posts were analyzed through a three-stage annotation pipeline: first filtering for topical relevance (Applicable vs Not Applicable), then classifying stigma presence (Stigma vs No Stigma), and finally applying fine-grained labels to capture specific types of stigma. Comments on these posts were separately annotated for support.

## Methodology

Annotation proceeded in three stages, each building on the output of the previous one.

### Level 1: Applicable vs Not Applicable

Posts were screened for topical relevance and labeled as either:
- **Applicable** – the post directly discussed sexual violence
- **Not Applicable** – the post did not

Only posts labeled Applicable were carried forward to the next stage.

### Level 2: Stigma vs. No Stigma

Applicable posts were assigned a binary label:
- **Stigma** – the post contained stigmatizing language, beliefs, or experiences
- **No Stigma** – the post did not

### Level 3: Fine-Grained Stigma Labeling

Posts labeled Stigma were further annotated using a taxonomy capturing specific types of stigma. Labels applied (multiple per post allowed):
- **Experienced** stigma
- **Internalized** stigma
- **Anticipated** stigma
- **Structural** stigma

Comments on these posts were also tagged for support and stigma content (Multiple allowed):
- **Information** support
- **Emotional** support
- **Esteem** support
- **Tangible** assistance
- **Group** interaction

## Dataset Structure

The annotated data is organized into three levels corresponding to the stages above.

### Level 1 — Applicable Labels

Contains all posts marked Not Applicable.

| Column | Description |
|---|---|
| `post_id` | Unique identifier for the post |
| `l1_label` | Relevance label (Applicable / Not Applicable) |
| `subreddit` | Subreddit the post was collected from |
| `timestamp` | Time the post was created |

### Level 2 — Stigma Labels

Contains posts that passed relevance filtering, labeled as Stigma or No Stigma.

| Column | Description |
|---|---|
| `post_id` | Unique identifier for the post |
| `l2_label` | Stigma label (Stigma / No Stigma) |
| `subreddit` | Subreddit the post was collected from |
| `timestamp` | Time the post was created |

### Level 3 — Fine-Grained Stigma and Comment Annotations

Contains fine-grained stigma labels along with associated comment-level annotations.

| Column | Description |
|---|---|
| `post_id` | Unique identifier for the post |
| `subreddit` | Subreddit the post was collected from |
| `comment_id` | Unique identifier for the comment |
| `created_utc` | Comment creation time (UTC) |
| `timestamp` | Time the comment was created |
| `support_tags` | Support type(s): Information, Emotional, Esteem, Tangible, and/or Group |
| `stigma_tags` | Fine-grained stigma type(s): Experienced, Internalized, Anticipated, and/or Structural |

## Repository Contents

- `Camera Ready Submission  - Dataset.csv` — Single file containing all annotation levels (Level 1, Level 2, and Level 3 data)

## Citation

If you use this dataset, please cite our paper.