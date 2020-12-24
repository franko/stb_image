project('stb_image', 'c', version: '2.26', default_options : ['c_std=gnu89'])

cc = meson.get_compiler('c')
libm = cc.find_library('m', required : false)

stb_image_include = include_directories('include')

install_headers('include/stb_image.h')
install_headers('include/stb_image_write.h')
install_headers('include/stb_image_resize.h')

subdir('src')
