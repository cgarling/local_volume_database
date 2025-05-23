# **local_volume_database** 

### DESCRIPTION:

The LVDB is a database of dwarf galaxies and star clusters in the Local Volume. The database is complete for dwarf galaxies within ~5 Mpc. 
The planned limiting distance is ~10+ Mpc (i.e. resolved stars with HST or JWST).  
The star cluster collections are currently limited to old star clusters/globular clusters in the Milky Way halo and globular clusters/star clusters hosted by low mass dwarf galaxies.

The main data tables are located in the release pages in `csv` and `fits` file formats. The data tables are also available in the [`data/`](data/) folder in `csv` format. 
A summary pdf document of the database content is available in the release page. 


Documentation: [readthedocs](https://local-volume-database.readthedocs.io/en/latest/index.html).

Overview paper: [arXiv](https://arxiv.org/abs/2411.07424) and  [ADS](https://ui.adsabs.harvard.edu/abs/2024arXiv241107424P/abstract).

The LVDB releases are also indexed on [zenodo](https://doi.org/10.5281/zenodo.14076714).

The tables can be directly loaded into Jupyter notebooks without having to download the repository:

    import astropy.table as table
    # loads the current dwarf galaxy data catalog from the release page (recommended)
    version_number_string = table.Table.read('https://raw.githubusercontent.com/apace7/local_volume_database/main/code/release_version.txt', format='ascii.fast_no_header')['col1'][0]
    dwarf_all = table.Table.read('https://github.com/apace7/local_volume_database/releases/download/'+version_number_string+'/dwarf_all.csv')


An interactive version of the LVDB is available here: [link](https://lvd-interactive.streamlit.app/) (made by Katya Gozman).

Community contributions to the LVDB are welcome. Please feel free to contract me with any questions about LVDB content and/or potential contributions. 

### INSTALLATION and USE:

Users that only want to use the catalogs do not need to install the package. 
The catalogs are available as csv and fits files in the release pages.
The package is focused on helper functions and yaml file access. 


The package is installable locally via pip:

```
git clone https://github.com/apace7/local_volume_database.git
cd local_volume_database
python -m build
pip install .
```

The `LVDBDIR` environment variable is required to point to the location of the input YAML files (/data_input/). 

### ACKNOWLEDGEMENT:

If you use this in your research please include a link to the github repository (https://github.com/apace7/local_volume_database) and cite the overview paper. It is highly encouraged to cite the input references of the database if they are used in your work. An example acknowledgement in LaTeX (with BibTeX below): This work has made use of the Local Volume Database\footnote{\url{https://github.com/apace7/local_volume_database}} \citep{Pace2024arXiv241107424P}. 

The BibTeX of the citation is available below and on [ADS](https://ui.adsabs.harvard.edu/abs/2024arXiv241107424P/exportcitation):

    @ARTICLE{Pace2024arXiv241107424P,
        author = {{Pace}, Andrew B.},
            title = "{The Local Volume Database: a library of the observed properties of nearby dwarf galaxies and star clusters}",
        journal = {arXiv e-prints},
        keywords = {Astrophysics - Astrophysics of Galaxies},
            year = 2024,
            month = nov,
            eid = {arXiv:2411.07424},
            pages = {arXiv:2411.07424},
            doi = {10.48550/arXiv.2411.07424},
    archivePrefix = {arXiv},
        eprint = {2411.07424},
    primaryClass = {astro-ph.GA},
        adsurl = {https://ui.adsabs.harvard.edu/abs/2024arXiv241107424P},
        adsnote = {Provided by the SAO/NASA Astrophysics Data System}
    }



