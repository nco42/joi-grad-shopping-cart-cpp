##############################################################################
# Project
project('joi-grad-shopping-cart-cpp', 'cpp', version: '1.0', meson_version: '>=1.4.0',
    default_options: ['cpp_std=c++20'])

gtest_proj = subproject('gtest')
gtest_dep = gtest_proj.get_variable('gtest_dep')

inc = [include_directories('include')]

lib_src = files('src/shopping_cart.cc')
app_src = lib_src + files('src/main.cc')

joi_app = executable(
	'joi-grad-shopping-cart-cpp',
	app_src,
)

test_src = files('test/shopping_cart_test.cc', 'test/test_main.cc')

joi_tests = executable('joi-grad-shopping-cart-cpp-test',
	lib_src + test_src,
	include_directories: [inc],
	dependencies: [
        gtest_proj.get_variable('gtest_dep'),
        gtest_proj.get_variable('gmock_dep'),
    ]
)

test('joi-grad-shopping-cart-cpp-test', joi_tests)
