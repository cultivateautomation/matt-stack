# matt-stack

This is the Hugo repository for the MattLincoln.net blog.

## Content Creation Guidelines

When adding new blog posts to this repository, you **MUST** use Hugo Page Bundles. Do not drop raw `.md` files into the `content/post` root directory.

### How to format a Page Bundle:
1. Create a new directory for your post: `content/post/your-post-title-slug/`
2. Create an `index.md` file inside that directory for the post content.
3. Place any associated images (like the header image) directly in that same directory.
4. Reference the header image in the `index.md` front matter like so: `image: your-header-image.jpg`