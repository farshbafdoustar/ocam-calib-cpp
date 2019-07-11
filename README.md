# ocam-calib-cpp
Omnidirectional camera calibration implementation c++

## installation
### Prequisites
1. OpenCV
2. [Ceres](http://ceres-solver.org/installation.html)
3. Eigen3 : When you installed Ceres., you have alreary installed Eigen3. See [here](http://ceres-solver.org/installation.html)

### Build
- git clone https://github.com/farshbafdoustar/ocam-calib-cpp.git
- cd ocam-calib-cpp
- mkdir build
- cd build
- cmake ..
- make -j8

### Usage
- cd build
- ./ocam-fisheye-calib -w=6 -h=8 -s=24 -o=camera.xml -op -oe -su imagelist.xml
- Parameters:
   - -w=<board_width>         : the number of inner corners per one of board dim
   - -h=<board_height>        : the number of inner corners per another board dimension
   - [-pt=<pattern>]          : the type of pattern: chessboard or circles' grid
   - [-n=<number_of_frames>]  : the number of frames to use for calibration (if not specified, it will be set to the number of board views actually available)
   - [-d=<delay>]             : a minimum delay in ms between subsequent attempts to capture a next view (used only for video capturing)
   - [-s=<squareSize>]        : square size in some user-defined units (1 by default)
   - [-o=<out_camera_params>] : the output filename for intrinsic [and extrinsic] parameters
   - [-op]                    : write detected feature points
   - [-oe]                    : write extrinsic parameters
   - [-zt]                    : assume zero tangential distortion
   - [-a=<aspectRatio>]       : fix aspect ratio (fx/fy)
   - [-p]                     : fix the principal point at the center
   - [-v]                     : flip the captured images around the horizontal axis
   - [-V]                     : use a video file, and not an image list, uses [input_data] string for the video file name
   - [-su]                    : show undistorted images after calibration
   - [input_data]             : input data, one of the following: 
      - text file with a list of the images of the board the text file can be generated with imagelist_creator
      - name of video file with a video of the board if input_data not specified, a live view from the camera is used
   

