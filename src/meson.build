stb_image_source = ['stb_image.c', 'stb_image_write.c', 'stb_image_resize.c']

stb_image_lib = static_library('stb_image',
    stb_image_source,
    include_directories: stb_image_include,
    install: true
)

pkg = import('pkgconfig')

pkg.generate(stb_image_lib,
    filebase : 'stb_image',
    name : 'stb_image',
    libraries : libm,
    description : 'image stb library for C/C++',
    url : 'https://github.com/nothings/stb',
)
