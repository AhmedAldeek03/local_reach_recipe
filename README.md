# Local Reach

A Drupal recipe that adds the **Local Reach** components to Drupal Canvas as code components.
They are rebuilt from the KHF `local_reach` custom module, with the same markup, CSS and
count-up animation, but with no PHP: everything ships as configuration.

## Components

| Component                          | Main props                                                         |
|------------------------------------|--------------------------------------------------------------------|
| Local Reach: Key figures           | Heading, icon, numbers, descriptions, number and line colors       |
| Local Reach: Progress bars         | Titles, numbers, total, icons, background, bar and icon colors     |
| Local Reach: Ring charts           | Title, icon, labels, percentages, numbers, colors                  |
| Local Reach: Country flags         | Heading, icon, flag images (alt text = country name), line color   |
| Local Reach: Institution summary   | Logo, number, text, number color                                   |

List props (numbers, titles, labels…) are matched by position: the first description belongs
to the first number, and so on. Numbers count up from 0 when they scroll into view, as in the
original blocks.

## Differences from the custom module

- **One group per Key figures component.** Place several components side by side for several
  groups.
- **Translations use Canvas**, not separate per-language fields.
- **One color set per Ring charts component**, instead of colors per ring.
- **Institution summary takes its values directly** (logo, number, text) instead of reading a
  taxonomy term.

## Requirements

- Drupal 11.3 or later
- [Drupal Canvas](https://www.drupal.org/project/canvas). The recipe installs it if it is
  missing, along with an Image media type for the image props.

## Installation

```bash
composer config repositories.local_reach_recipe '{"type": "vcs", "url": "https://github.com/AhmedAldeek03/local_reach_recipe", "no-api": true}'
composer require drupal/local_reach_recipe:1.0.x-dev@dev
drush recipe ../recipes/local_reach_recipe
drush cache:rebuild
```

The components then appear in the Canvas component library under **Code**.
