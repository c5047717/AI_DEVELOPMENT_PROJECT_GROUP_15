# Cricket Ball Detection Notebook

## Video folder setup

### Google Colab

1. Upload your GoPro MP4 clips into a folder in Google Drive.
2. The notebook expects the folder to be:
   `/content/drive/MyDrive/ball_trajectory/`
3. If the folder is missing, the notebook will print:
   `Folder not found: /content/drive/MyDrive/ball_trajectory/`

### Confirm files

The notebook will search for `.MP4` files in the folder and report:
- number of files found
- file names
- file sizes

### If files are not found

Run this command in Colab to locate your GoPro clips:

```bash
!find /content/drive/MyDrive -name "GH01*.MP4" -type f
```


###Required Python packages
The notebook is tested with:

numpy==1.26.4
compatible pandas

**Why this is important**

pandas depends on NumPy internals.
numpy==1.26.4 is the tested version for stable compatibility with this notebook setup.
Using the exact NumPy version avoids runtime errors during data processing and CSV export.
