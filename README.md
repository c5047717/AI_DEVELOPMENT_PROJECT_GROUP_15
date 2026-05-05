# Cricket Ball Detection Notebook

## How to Run

1. Open `cricket_ball_detection.ipynb` in Google Colab.
2. Set runtime to T4 GPU:
   - `Runtime > Change runtime type`
   - CPU also works, but is significantly slower for optical flow and Hough processing.
3. Run the installation cell.
   - All packages install with individual error handling.
4. Update `VIDEO_FOLDER` to the Google Drive folder containing your `GH01*.MP4` files.
   - Set `VIDEO_INDEX` to select which clip to process:
     - `0` for `GH010059`
     - `1` for `GH010060`
     - etc.
5. Set `MAX_FRAMES` to `300` for initial testing (approximately 10 seconds).
   - Once results are satisfactory, set `MAX_FRAMES = None` for the full clip.
6. Run all cells:
   - `Runtime > Run all`
   - The notebook will run all three detection methods, perform ensemble fusion, and generate the annotated output video with bounding boxes and trajectory trail.
7. Use the final download cell to zip all outputs:
   - `ball_detection_output.mp4` (annotated video)
   - `ball_detections.csv` (frame-by-frame positions)
   - method comparison chart
   - optical flow visualisation
   - Hough detection samples
   - trajectory plot

### Troubleshooting

- If a `numpy.rec` error occurs after the video output cell:
  - change NumPy to `1.26.4` in the installation cell
  - restart the runtime
- Processing time of approximately 1 hour for 162 frames is expected and normal.

---

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
