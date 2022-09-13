# Installation Guide of Things
Contents<br>
1. [How to Set Up a Conda Environment](#How-to-Set-Up-a-Conda-Environment)<br>
2. [GDAL For Windows (outside conda environment)](#GDAL-For-Windows-outside-conda-environment)<br>
3. [GDAL For Windows (inside conda environment)](#GDAL-For-Windows-inside-conda-environment)<br>
4. [GDAL for Linux (inside conda environment)](#GDAL-for-Linux-inside-conda-environment)<br>
5. [Rasterio (inside conda environment)](#Rasterio-inside-conda-environment)


<h3>How to Set Up a Conda Environment?<a name="How-to-Set-Up-a-Conda-Environment"></a></h3>
A virtual environment like conda helps us to create isolated spaces to keep the versions of packages of a specific project. To create a conda environment use the command:<br>
<code>conda create --name your_conda_env_name python=insert_version</code><br>
For linux, to prepare bash environment for use of command <code>conda activate</code> anywhere, use the following command:<br>
<code>conda init bash</code><br>
To activate the created conda environment use<br>
<code>conda activate your_conda_env_name</code><br>
To install a package a package, use any of the following command:<br>
<ul>
<li><code>conda install package_name</code> (From official <a href="https://www.anaconda.com/products/distribution">Anaconda</a> distribution)</li> 
<li><code>conda install --channel=conda-forge package_name</code> (From conda-forge channel often contains the latest version of a package)</li>
<li><code>pip install package_name</code> (From <a>PyPI</a>, a package repository of open-source Python libraries. To make use of <coda>pip</code> commands inside conda use <code>conda install pip</code>)</li>
</ul>
To deactivate or get out of the created conda environment use<br>
<code>conda deactivate</code><br>

<h3>GDAL For Windows (outside conda environment) <a name="GDAL-For-Windows-outside-conda-environment"></a></h3>
STEP 1: Go to this <a href="https://www.gisinternals.com/release.php">Link</a> and select the package suited for your architecture. Select the msi installer of GDAL according to the version of python in your environment. Also, choose the insaller with description <code>Installer for the GDAL python bindings (requires to install the GDAL core)</code>.<br>

STEP 2: Install GDAL through the downloaded msi installer.<br>

STEP 3: Check the version of the installed GDAL using the command <code>gdalinfo --version</code>. Remember the version.<br>

STEP 4: Go to command prompt and run the following seperately:
<ul>
<li><code>setx PATH "%PATH%;C:\Program Files (x86)\GDAL"</code></li>
<li><code>setx PATH "%GDAL_DATA%;C:\Program Files (x86)\GDAL\gdal-data"</code></li>
<li><code>setx PATH "%GDAL_DRIVER_PATH%;C:\Program Files (x86)\GDAL\gdalplugins"</code></li>
<li><code>setx PATH "%GDAL_VERSION%;insert_gdal_version_here"</code></li>
</ul>
NOTE: The above commands are for 32-bit Windows. For 64-Bit, just remove the <code> (x86)</code>. Don't forget to remove the space before (x86).

<h3>GDAL For Windows (inside conda environment) <a name="GDAL-For-Windows-inside-conda-environment"></a></h3>
STEP 1: Run the command <code>conda install -c conda-forge gdal</code><br>

STEP 2: Check the version of the installed GDAL using the command <code>gdalinfo --version</code>. Remember the version.

STEP 3: Go to command prompt and run the following seperately:
<ul>
<li><code>setx PATH "%PATH%;C:\Program Files (x86)\GDAL"</code></li>
<li><code>setx PATH "%GDAL_DATA%;C:\Program Files (x86)\GDAL\gdal-data"</code></li>
<li><code>setx PATH "%GDAL_DRIVER_PATH%;C:\Program Files (x86)\GDAL\gdalplugins"</code></li>
<li><code>setx PATH "%GDAL_VERSION%;insert_gdal_version_here"</code></li>
</ul>
NOTE: The above command is for 32-bit Windows. For 64-Bit, just remove the <code> (x86)</code>. Don't forget to remove the space before (x86).

<h3>GDAL for Linux (inside conda environment)<a name="GDAL-for-Linux-inside-conda-environment"></a></h3>
To install gdal, use any of the following commands:<br>
<code>conda install -c conda-forge gdal</code> or<br>
<code>pip install GDAL</code>

<h3>Rasterio (inside conda environment)<a name="Rasterio-inside-conda-environment"></a></h3>
STEP 1: Install GDAL using guide above.<br>
STEP 2: Run the following command individually:
<ul>
<li><code>conda install -c conda-forge fiona</code></li>
<li><code>conda install -c conda-forge pyproj</code></li>
<li><code>conda install -c conda-forge shapely</code></li>
<li><code>conda install -c conda-forge rasterio</code></li>
</ul>


