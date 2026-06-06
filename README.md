# matt-stack

This is the Hugo repository for the MattLincoln.net blog.

## Content Creation Guidelines

When adding new blog posts to this repository, you **MUST** use Hugo Page Bundles. Do not drop raw `.md` files into the `content/post` root directory.

### How to format a Page Bundle:
1. Create a new directory for your post: `content/post/your-post-title-slug/`
2. Create an `index.md` file inside that directory for the post content.
3. Place any associated images (like the header image) directly in that same directory.
4. Reference the header image in the `index.md` front matter like so: `image: your-header-image.jpg`

### Header Image Selection Workflow:
When selecting a header image, do **not** use AI generation. Instead:
1. Identify the conceptual theme of the post and brainstorm 3-4 symbolic metaphors.
2. **Review the 5 most recently published posts** in the `content/post/` directory to ensure your chosen metaphor hasn't been used recently (e.g., don't use a "crossroads" image if the last post used a "signpost").
3. Search Unsplash for a high-quality photograph matching your metaphor.
4. Download the image forcing a standard 16:9 aspect ratio and centered crop (`w=1200&h=630&fit=crop&crop=center`) so the focal point is preserved and the layout doesn't break.