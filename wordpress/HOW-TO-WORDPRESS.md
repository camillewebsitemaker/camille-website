# WordPress setup (so formatting matches)

Your original file was breaking because it contained email text above `<!DOCTYPE html>` and got truncated. This project now has clean page files and WordPress-safe snippets.

## 1) Add the site CSS once
- In WordPress admin, go to **Appearance → Customize → Additional CSS**.
- Paste all contents of `wordpress/wordpress-styles.css` and publish.

## 2) Create each page in WordPress
- Pages to create: Home, About, Books, Poems, Press, Scholarship, Contact.
- For each page, add a **Custom HTML** block and paste the matching file from `wordpress/pages/`.

## 3) Important editor settings
- Use **Custom HTML block**, not Paragraph block.
- If your theme has a narrow content width, set page template to **Full Width** (or equivalent).
- Disable page title in theme settings if you want only the designed title.

## 4) Menu links
- Build menu under **Appearance → Menus** and link pages normally.
- If slug names differ, update the links inside each snippet.

## 5) If spacing still looks off
Some themes add extra margins to blocks. Add this in Additional CSS after the pasted stylesheet:

```css
.wp-block-group, .wp-block-post-content, .entry-content {
  max-width: none !important;
}
.entry-content > * {
  margin-top: 0;
  margin-bottom: 0;
}
```
