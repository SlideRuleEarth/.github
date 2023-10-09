## SlideRule: an open framework for on-demand processing of science data in the cloud

> The SlideRule project offers a new paradigm for NASA archival data management – rapid processing and delivery of customizable data products, rather than hosting large volumes of derivative products.

Repository organization:
* [sliderule-python](https://github.com/ICESat2-SlideRule/sliderule-python) contains example notebooks demonstrating SlideRule capabilities. Start here if you are a science user.
* [sliderule](https://github.com/ICESat2-SlideRule/sliderule) contains the server-side and Python client code, along with the H5Coro driver; mostly C++ and Lua. Start here if you are interested in contributing to the development of SlideRule.
* [paper](https://github.com/ICESat2-SlideRule/paper) contains materials for the JOSS publication describing SlideRule (https://joss.theoj.org/papers/10.21105/joss.04982).

The scalable server-side components of SlideRule run in the AWS cloud with optimized functions to read HDF5 data hosted by NASA in S3 cloud object storage. While SlideRule can be accessed by any HTTP client (e.g., curl) through GET and POST requests, the sliderule-python client provides a user-friendly API for easy interaction with SlideRule's web services. The client library returns standard Python data containers (i.e., Pandas DataFrame) and facilitates serialization with provenance metadata for reproducible science.

SlideRule uses a plugin framework to support different NASA missions and data products. The ICESat-2 SlideRule plugin offers customizable algorithms to process the archive of low-level data products from the NASA [Ice Cloud and land Elevation Satellite-2 (ICESat-2)](https://icesat-2.gsfc.nasa.gov/) laser altimetry mission. The user defines a geographic area of interest and key processing parameters via an interactive web interface or the API, and SlideRule returns high-level surface elevation point cloud products in seconds to minutes, enabling rapid algorithm development, visualization and scientific interpretation. Additional plugins include support for sampling raster datasets like ArcticDEM, REMA, and Landsat's HLS.  There is also a plugin for the GEDI mission that includes some subsetting capabilities with additional features in-progress.

![SlideRule Architecture](https://slideruleearth.io/rtd/_images/sys_block_diagram.png)


