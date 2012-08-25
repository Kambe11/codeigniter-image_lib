CodeIgniter Image_lib
=============

Extended image library for CodeIgniter based on Image_lib / CI2.1.2

Installation
-------

Copy application/libraries/Image_lib.php to YOUR_CI_PATH/application/libraries/ .


Changes from Image_lib / CI2.1.2
------------
Added : 
* variables(flags) : "rotate_by_exif" and "strip_exif".
* method : _image_mirror_gd()

Modified:
* image_process_imagemagick() : Negative parameters are acceptable in "x_axis" and "y_axis".
* image_process_imagemagick() : Rotate image resource by "Orientation" tag in Exif.
* image_process_imagemagick() : Strip Exif.
* image_process_gd() : Rotate image resource by "Orientation" tag.


Details
------------

### rotate_by_exif

Whether to enable rotating an image or not.
If set and non-zero, Rotate an image resource by a value of "Orientation".
Default: TRUE

### strip_exif

Whether to enable deleting an Exif or not.
Default: TRUE

### Usage

    $config_image = array(
      'image_library' => 'imagemagick',
      'library_path' => '/usr/bin/convert',
      'source_image' => '/var/www/html/IMAGE_SOURCE.jpg',
      'new_image' => '/var/www/html/IMGE_NEW.jpg',
      'width' => 640,
      'maintain_ratio' => TRUE,
      'rotate_by_exif' => TRUE,
      'strip_exif' => TRUE,
    );
    $this->load->library('image_lib', $config_image);
    $this->image_lib->resize();

OR

    $config_image = array(
      'image_library' => 'gd2',
      'source_image' => '/var/www/html/IMAGE_SOURCE.jpg',
      'new_image' => '/var/www/html/IMGE_NEW.jpg',
      'width' => 640,
      'maintain_ratio' => TRUE,
      'rotate_by_exif' => TRUE,
      'strip_exif' => TRUE,
    );
    $this->load->library('image_lib', $config_image);
    $this->image_lib->resize();
