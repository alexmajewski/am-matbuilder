# Multi-Engine Material Builder

_The work is still in progress, but the tool is functional_

A tool for automated generation of multi-engine materials out of PBR texture images. Created for Solaris, but it could theoretically be used in a regular material context.

https://github.com/alexmajewski/am-matbuilder/assets/77795178/fd592ca7-1a0a-4a51-b236-9ce88f9a6075

# How to use

Click *Add Images* or drag & drop image files from your drive into the drop zone.

![am-matbuilder-drop](https://github.com/alexmajewski/am-matbuilder/assets/77795178/319156dd-b749-4be0-b145-d25adce070f6)

Next, assign map types to each image. The tool will attempt figuring it out automatically from name.

![am-matbuilder-assign-type](https://github.com/alexmajewski/am-matbuilder/assets/77795178/251cbdcf-3c5e-4aa4-91df-8ab154dc1812)

Click Generate Setup to create nodes in the Network Editor with the images from the list using selected engine templates.

![am-matbuilder-generate](https://github.com/alexmajewski/am-matbuilder/assets/77795178/e919d69e-ce59-4ee7-97f1-f2f9c0efec0e)

## How it works

This tool builds its interface procedurally based on .json templates in the `/engines/` folder. They serve as a recipe for both the creation of GUI checkboxes and the nodes in the Network Editor.

This means you, the user, have the full control over the engines and setups this tool can work with.

# Creating Your Own Templates

You can create your own templates for unsupported engines or different node setups.

All you have to do is create the nodes you want to save as a template, then open the cog wheel menu, click *New Template*, fill the input fields, and hit *Save Template*.

This will save the selected hierarchy of nodes, and will note down any parameters that are set to anything other than default values.

### Telling the template which nodes require a map type

You can do that by adding a `_map_*type*` suffix to a node’s name. For example `_map_basecolor`

![am-matbuilder-maps](https://github.com/alexmajewski/am-matbuilder/assets/77795178/e6b283f1-ce5d-4a2e-bdf7-634e17279e46)

This type of a suffix will be recognized by the tool and saved in the .json template file.
