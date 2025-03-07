# Media Hosting Configuration

## Recommended Free Cloud Storage Solutions

### 1. GitHub LFS (Large File Storage)
- Perfect for version-controlled media files
- Free tier: 1GB storage and 1GB bandwidth/month
- Setup instructions in `.gitattributes`

### 2. Cloudinary
- Excellent for images and videos
- Free tier: 25 credits (~25GB storage)
- Auto-optimization and responsive images

### 3. Archive.org
- Ideal for public domain content
- Unlimited storage for public files
- Permanent archival

## Implementation Steps

1. For PDFs:
   - Use GitHub LFS
   - Add to `.gitattributes`:
   ```
   *.pdf filter=lfs diff=lfs merge=lfs -text
   ```

2. For Images:
   - Use Cloudinary
   - Example usage:
   ```html
   ![Image Title](https://res.cloudinary.com/your-cloud-name/image/upload/your-image.jpg)
   ```

3. For Audio/Video:
   - Use Archive.org for public content
   - Use Cloudinary for private content

## Directory Structure
```
/assets
  /documents  # For PDFs
  /media      # For audio/video
  /images     # For images
```

## Performance Optimization

1. Lazy loading for images
2. Progressive loading for videos
3. Cloudinary's auto-format and compress
4. Browser caching headers

## Implementation Notes

1. Add necessary front matter variables:
   ```yaml
   ---
   cloudinary_url: your-cloud-name
   archive_org_id: your-archive-id
   ---
   ```

2. Update `_config.yml` with media settings
3. Implement proper cache headers
4. Use responsive images

This configuration ensures efficient media delivery while maintaining site performance.