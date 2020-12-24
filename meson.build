project('stb_image', 'c', version: '2.26', default_options : ['c_std=gnu89'])

cc = meson.get_compiler('c')
libm = cc.find_library('m', required : false)

stb_image_include = include_directories('include')

image_formats = [
    {'name': 'jpeg',   'def': 'JPEG'},
    {'name': 'png',    'def': 'PNG'},
    {'name': 'bmp',    'def': 'BMP'},
    {'name': 'psd',    'def': 'PSD'},
    {'name': 'tga',    'def': 'TGA'},
    {'name': 'gif',    'def': 'GIF'},
    {'name': 'hdr',    'def': 'HDR'},
    {'name': 'imgpic', 'def': 'PIC'},
    {'name': 'pnm',    'def': 'PNM'},
]

stb_image_cflags = []
# The flags below disable support for some image formats but only
# in std_image.h reader functions.
foreach format : image_formats
    if not get_option(format['name'])
        stb_image_cflags += '-DSTBI_NO_' + format['def']
    endif
endforeach

install_headers('include/stb_image.h')
install_headers('include/stb_image_write.h')
install_headers('include/stb_image_resize.h')

subdir('src')
