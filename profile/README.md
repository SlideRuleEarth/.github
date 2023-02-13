## SlideRule: an open framework for on-demand processing of science data in the cloud 

> The SlideRule project offers a new paradigm for NASA archival data management – rapid processing and delivery of customizable data products, rather than hosting large volumes of derivative products.

Repository organization:
* [sliderule-python](https://github.com/ICESat2-SlideRule/sliderule-python) contains the Python client and example notebooks demonstrating SlideRule capabilties. Start here if you are a science user.
* [sliderule](https://github.com/ICESat2-SlideRule/sliderule) contains the server-side code and H5Coro driver, mostly C++ and Lua.
* [sliderule-docs](https://github.com/ICESat2-SlideRule/sliderule-docs) contains documentation and rendered html for the website
* [paper](https://github.com/ICESat2-SlideRule/paper) contains materials for the JOSS publication describing SlideRule (https://joss.theoj.org/papers/10.21105/joss.04982)

The scalable server-side components of SlideRule run in the AWS cloud with optimized functions to read HDF5 data hosted by NASA in S3 cloud object storage. While SlideRule can be accessed by any HTTP client (e.g., curl) through GET and POST requests, the sliderule-python client provides a user-friendly API for easy interaction with the SlideRule service. The client library returns standard Python data containers (i.e., Pandas DataFrame) and facilitates serialization with provenance metadata for reproducible science.

SlideRule uses a plugin framework to support different NASA missions and data products. The ICESat-2 SlideRule plugin offers customizable algorithms to process the archive of low-level data products from the NASA [Ice Cloud and land Elevation Satellite-2 (ICESat-2)](https://icesat-2.gsfc.nasa.gov/) laser altimetry mission. The user defines a geographic area of interest and key processing parameters via an interactive web interface or the API, and SlideRule returns high-level surface elevation point cloud products in seconds to minutes, enabling rapid algorithm developent, visualization and scientific interpretation.

![SlideRule Architecture](https://github.com/ICESat2-SlideRule/paper/blob/main/paper/sliderule_arch_whitebg.jpg)
