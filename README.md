# Webpage from Jupyter notebooks

## Notes from the original [ipynb website](https://stephenslab.github.io/ipynb-website)

+ You can add option `-j` to the command if you want to control the 
  number of parallel processes that generate the notebook. For example
  `-j 8` uses 8 processes.

+ The `include_dir` setting in `config.yml` specifies the project
  subdirectories containing Jupyter notebooks to render into
  webpages. If no `index.ipynb` file is provided within a given
  subdirectory, an index will automatically be generated that lists
  links to all notebooks under that directory.

+ There is also the option of adding a table of contents to each
  notebook by setting `notebook_toc: True` in `config.yml`.

+ For the table of contents and the automatically generated index, it
  is recommended that the notebooks have descriptive names; e.g.,
  `Plot_station_map.ipynb`. All underscores are automatically treated
  as spaces, so `Plot_station_map.ipynb` will show as "Plot station
  map" in the index file and table of contents.

+ So far, only the Cerulean, Flatly and Readable Bootstrap themes have
  been adapted and tested for this framework. It is possible to select
  other themes (see [here](https://bootswatch.com) for a larger
  collection), although they may not work as well. Also note that
  there may be style conflicts or inconsistencies in the included CSS
  files; please report these style conflicts by posting an
  [Issue](https://github.com/stephenslab/ipynb-website/issues).

+ Initially, in your new project directory, clean up and then re-generate all the webpages using the SoS release script:

   ```bash
   sos run release.sos clean
   sos run release.sos -s force
   ```

   Or, simply:

   ```bash
   ./release.sos clean
   ./release.sos -s force
   ```
   if `release.sos` is granted executable permission.

+ Modify the website settings by editing `config.yml`. See the
  comments in this file for more detailed instructions. 
  Copy, rename or delete the notebooks in the "analysis", "setup"
  and "license" directories. Edit the notebooks interactively in Jupyter.
  After you are satisfied with your changes, re-build the modified
  webpages by running `sos run release.sos`, or use
  `sos run release.sos -s force` to re-build all the webpages,
  then commit your changes to the git repository.

+ Whenever you make global changes to the website (e.g., you change
  the Boostrap theme in `config.yml`), use the `-s force` option to force
  updates to all the webpages, not just the ones that have been modified.

+ The website is built by [`jnbinder`](https://github.com/vatlab/jnbinder)
  which does not make any formal releases. This repo releases / ships with
  its latest stable version.
  
  To upgrade `jnbinder` to its latest, type:
  ```
  ./release.sos upgrade-jnbinder
  ```
## License
Copyright (C) 2019-today Leonardo de Oliveira Martins

The Jupyter notebooks (that is, the content created here) is free software.
You can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation (http://www.gnu.org/copyleft/gpl.html).

## Credits of original [ipynb website](https://stephenslab.github.io/ipynb-website):
Please see [the ipynb website project](https://github.com/stephenslab/ipynb-website#credits) for complete credits and
license of the website layout creator. 

Peter Carbonetto and Gao Wang<br>
Dept. of Human Genetics, University of Chicago<br>
Copyright (c) 2017 under the terms of the [MIT license](https://opensource.org/licenses/MIT).
