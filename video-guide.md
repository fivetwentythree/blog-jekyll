# Adding Videos to Your Site

## Using the Video Include Template

This site supports embedding videos using a custom video include template that provides responsive playback and consistent styling.

### Basic Usage

To add a video to any post or page, use the following include syntax:

```liquid
{% include video.html url="/assets/media/your-video.mp4" %}
```

### Full Options

The video include supports several options:

```liquid
{% include video.html 
    url="/assets/media/your-video.mp4"
    type="video/mp4"
    poster="/assets/images/video-thumbnail.jpg"
    caption="Your video caption here"
%}
```

### Parameters

- `url`: (Required) Path to your video file
- `type`: (Optional) Video MIME type (defaults to video/mp4)
- `poster`: (Optional) Thumbnail image to show before video plays
- `caption`: (Optional) Caption text to display below the video

## Video File Guidelines

1. Place video files in the `/assets/media/` directory
2. Use MP4 format with H.264 encoding for best browser compatibility
3. Keep file sizes reasonable (compress when possible)
4. Consider providing multiple resolutions for different devices

## Example Implementation

Here's a complete example for a blog post:

```markdown
---
layout: post
title: Post with Video
---

## My Video Section

{% include video.html 
    url="/assets/media/demo-video.mp4"
    poster="/assets/images/demo-thumbnail.jpg"
    caption="Demo video showing our new feature"
%}
```

The video will be displayed responsively, maintaining aspect ratio and providing standard HTML5 video controls.

## Performance Considerations

- Videos are loaded with `preload="metadata"` to minimize initial page load
- The container is styled for responsive playback
- Captions are styled consistently with the site's typography
- Custom controls maintain the site's aesthetic