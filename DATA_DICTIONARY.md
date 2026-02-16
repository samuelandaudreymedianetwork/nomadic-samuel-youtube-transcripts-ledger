# Data Dictionary — Nomadic Samuel YouTube Transcripts (Curated, EN — Full Transcripts Only)

| Field | Type | Description |
|---|---:|---|
| id | string | Stable record id (first 16 hex chars of SHA1(video_id)). |
| content_hash | string | SHA1 hash of `text` (integrity / dedupe). |
| video_id | string | YouTube video id. |
| url | string | Canonical YouTube watch URL. |
| position | integer | Position in this curated release (1-indexed). |
| published_at | string | ISO-8601 timestamp from the curated list (YouTube publish time). |
| video_date | string | YYYY-MM-DD derived from `published_at`. |
| title | string | Video title from the curated list. |
| youtube_title | string | Same as `title` (kept for compatibility with other Samuel & Audrey datasets). |
| lang | string | Language code (`en`). |
| channel | string | Channel name (`Nomadic Samuel`). |
| domain | string | Domain of the source platform (`youtube.com`). |
| source | string | Dataset slug (`nomadic-samuel-youtube-transcripts`). |
| caption_source | string | Source of caption files (`srt_archive`). |
| caption_track_kind | string | Caption track kind (unknown/not provided). |
| view_count | integer | View count captured in the curated export. |
| tags | string | Raw comma-separated tag string from the curated export. |
| tags_list | array[string] | Tags split into a list (trimmed). |
| text | string | Plain text transcript derived from SRT captions (minimal punctuation spacing normalization). |
| text_with_breaks | string | Transcript preserving caption line breaks (blank line between captions). |
| srt | string | Full raw `.srt` content including timestamps. |
| original_filename | string | Original SRT filename used for this record. |
| missing_transcript | boolean | Always `false` in this build (rows without transcripts were excluded). |
