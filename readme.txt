Implementation of lines() class
There are three basic methods:
1)	__init__(self, dist, mtx, M, invM) – initialize an instance, dist, mtx – distortion coefficients and camera matrix, respectively, M, invM – matrices of prespective and inverse perspective transforms, respectively
2)	set_params(self, draw='region', single_mode=False,  window_width=50, window_height=80, margin=50, curve_line_margin=50, mag_min=0.05, mag_max=1, dir_min=0., dir_max=0.9*np.pi,  init_cmap='BGR', hls_channels=['S', 'L'],  max_to_keep=5, min_points=50) – set parameters for video processing
parameters:
draw [‘region’, ‘lines’] – draw a filled polygon or just lines
single_mode – if set to true, searches lines from scratch for every frame, otherwise uses lines from the previous frame and makes search only in curve_line_margin (in pixels) region around them
window_width – width of search window
window_height – height of search window
margin – width of search zone for single_mode == True
curve_line_margin  - margin for single_mode == False
mag_min, mag_max, dir_min, dir_max – parameters for sobel filtering
hls_channels – which of HLS channels to use for processing
max_to_keep – number of frames used to average line drawing
min_points – threshold number of points for line searching
3)	get_lines(self, img) – finds lines and draws then on the image
Example usage:
line_gen = lines(dist, mtx, M, invM)
line_gen.set_params()
result = line_gen.get_lines(img)

