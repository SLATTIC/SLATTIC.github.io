# Speech & Language @ TTIC, Group Website

Web code and maintenance instructions for the S&L Group website 2024 version.

## Build and Deployment

### Dependencies

- Ruby >= 2.5.0
- [Jekyll](https://jekyllrb.com/docs/installation/)
- bibble (python2 version)

### Build

Invoke *make* to build the site:

```
make
```

This will generate a deployable site under the ```_site``` folder.

For development, use the ```serve``` option to host a site locally:

```
make serve
```

### Deployment

Make sure to change the base link in ```_config.yml``` for all file links for work properly. This field should be empty when developing with ```make serve```.

To deploy the site, copy the ```_site``` folder into your web host and grant the appropriate permissions.

## Content Maintenance

### Adding a person

Adding a person to this webpage normally requires modifications to the corresponding YAML (.yml) file. Within the YAML file, choose an unused key and fill-in the appropriate fields.

Go to ```_data/people.yml```, each entry contains the following fields:

- *display_name*: Name of the person
- *webpage*: Link to the person's webpage (Optional)
- *role*: one of {*faculty*, *phd*, *alum-faculty*, *alum-phd*, *alum-visit/uc*}
- *image*: Link to the person's portrait image (For non-alumni only)
- *bio*: The person's position/placement (Optional)

Example:

```
prof-zs:
    display_name: "Zhewei Sun"
    webpage: https://zhewei-sun.github.io/
    role: faculty
    image: https://ttic.edu/img/sun_small.jpg
    bio: Research Assistant Professor
```

**Note**: To deal with a potential formatting issue, we need an even number of people within each *role* group. To do this, simply add a person with an empty name under the appropriate *role* group. The website code will ignore this entry and only creating the box for formatting purposes.

```
prof-pad:
    display_name: ""
    role: faculty
```

### Adding a news

To add a news post, create a markdown file and place it under ```_posts```. To create the markdown file, either use the IPython notebook ```dev/News.ipynb``` or start from an existing file. You will need to supply the following information:

- *news*: The text of the news post
- *icon*: An icon to be displayed alongside the new post, see ```dev/News.ipynb``` for a cheat sheet.
- *quarter*: The academic quarter to be displayed alongside the news text

**Note:** If you decide to copy and modify an existing file, make sure you update the date in the file name. The news entries are sorted based on the file names.

### Adding a resource

Go to ```resources.html``` and add the content directly in html (within an <li> tag).
``
