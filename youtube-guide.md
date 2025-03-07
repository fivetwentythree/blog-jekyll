# Adding Videos to Your Site

This site supports embedding both YouTube videos and local video files using custom include templates that provide responsive playback and consistent styling.

## Using the Video Include Template for Local Videos

### Basic Usage

To add a local video to any post or page, use the following include syntax:

```liquid
{% include video.html url="/assets/media/your-video.mp4" %}
```

### Full Options for Local Videos

The video include supports several options:

```liquid
{% include video.html 
    url="/assets/media/your-video.mp4"
    type="video/mp4"
    poster="/assets/images/video-thumbnail.jpg"
    caption="Your video caption here"
%}
```

### Parameters for Local Videos

- `url`: (Required) Path to your video file
- `type`: (Optional) Video MIME type (defaults to video/mp4)
- `poster`: (Optional) Thumbnail image to show before video plays
- `caption`: (Optional) Caption text to display below the video

## Using the YouTube Include Template

### Basic Usage

To add a YouTube video to any post or page, use the following include syntax:

```liquid
{% include youtube.html id="VIDEO_ID" %}
```

Replace `VIDEO_ID` with the ID of your YouTube video. The video ID is the string that appears after `v=` in the YouTube URL. For example, if your video URL is `https://www.youtube.com/watch?v=dQw4w9WgXcQ`, the ID would be `dQw4w9WgXcQ`.

### Full Options for YouTube Videos

The YouTube include supports several options:

```liquid
{% include youtube.html 
    id="VIDEO_ID"
    title="Video Title"
    start="30"
    width="800px"
    height="75%"
    caption="Your video caption here"
%}
```

### Parameters for YouTube Videos

- `id`: (Required) The YouTube video ID
- `title`: (Optional) Title for the video iframe (defaults to 'YouTube video player')
- `start`: (Optional) Start time in seconds
- `width`: (Optional) Custom width for the video container (e.g., '800px', '100%')
- `height`: (Optional) Custom height for the video wrapper (e.g., '75%', '400px')
- `caption`: (Optional) Caption text to display below the video

## Example Implementation

Here's a complete example for a blog post with both types of videos:

```markdown
---
layout: post
title: Post with Videos
---

## Local Video

{% include video.html 
    url="/assets/media/demo.mp4"
    poster="/assets/images/demo-thumbnail.jpg"
    caption="A local video demonstration"
%}

## YouTube Video

{% include youtube.html 
    id="dQw4w9WgXcQ"
    title="Never Gonna Give You Up"
    width="800px"
    height="75%"
    start="30"
    caption="Rick Astley's classic hit"
%}
```

## Performance Considerations

- Videos are loaded with lazy loading enabled to minimize initial page load
- The container maintains proper aspect ratios for responsive playback
- Captions are styled consistently with the site's typography
- For YouTube videos, privacy-enhanced mode is used for better user privacy
- Local videos use preload="metadata" to improve initial page load performance