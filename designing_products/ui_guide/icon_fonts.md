# [Designing Products](../../designing_products.md) / UI Guide / Updating our Icon Fonts


#### Tools Used

 - [Fontastic](http://app.fontastic.me/)
 - Adobe Illustrator


#### Adding an Icon — Process

 1. Open the icon font in Illustrator (`~/.ep/assets/iconfont.ai`)
 2. Make sure only a single layer is visible
 3. Select everything and Expand Strokes and Fills (**Object** / **Expand..**) (icon fonts can't use strokes)
 4. Used the **Pathfinder** palette to union shapes (or to subtract negative space)
 5. Choose **Save a Copy...** and save the icon as an SVG (don't use **Export for Screens...** For some reason SVGs exported that way don't import right into Fontastic)
 6. Upload the icons to Fontastic (**Menu** / **Add icons to this set** for the CPH set)
 7. (Optional) Click **Customize** and rename the icon
 8. Edit `~/.ep/libexec/ep-font:publish` and add the new icon to the list of glyphs in the `ICONS` constant
 9. From the command line, run `ep font:publish <font> <version>`, being sure to increment the version number from whatever is currently being used in Production (since the current version is probably cached).


#### Links

`ep font:publish` publishes references pages for the fonts. As of 2018 Dec 17, the current versions were:

- https://s3.amazonaws.com/cphepdev/360icons/1.6/reference.html
- https://s3.amazonaws.com/cphepdev/lsbicons/0.15/reference.html
