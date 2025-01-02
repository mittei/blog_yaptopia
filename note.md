## Neocities

- Neocities actually modifies html on the fly when requested
  - e.g. inserts charset `<meta>` if it's missing

## Folders

- public: output
- assets
  - Won't get included in `public` if you don't reference them using `resources.Get` etc.

## Plan

- layout
  - copy this https://www.brycewray.com/posts/2022/07/really-getting-started-hugo-four-steps/
  - no css framework
- static site generator
  - hugo (without a theme)
    - tutorial: https://www.brycewray.com/posts/2022/07/really-getting-started-hugo-four-steps/
- no responsive font size (for now)
- break points should be set where they make sense in terms of user experience
- reference
  - clamping font-size can cause problems: https://adrianroselli.com/2019/12/responsive-type-and-zoom.html
  - responsive design guideline: https://old.reddit.com/r/web_design/comments/11s8wqa/whats_the_current_best_way_for_responsive_design/jceh5gr/
