# HtmlTestRunner


[![Pypi link](https://img.shields.io/pypi/v/html-testRunner.svg)](https://pypi.python.org/pypi/html-testRunner)
[![Travis job](https://img.shields.io/travis/oldani/HtmlTestRunner.svg)](https://travis-ci.org/oldani/HtmlTestRunner)



HtmlTest runner is a unittest test runner that save test results
in Html files, for human readable presentation of results.

This Package was inspired in ``unittest-xml-reporting`` and
``HtmlTestRunner by tungwaiyip``.

This project was created due to needs of getting human readables reports 
for test runned, i found one but was lack and with a lot of bad practice,
but i liked how ``xml-reporting`` works. So i create this one that 
incorporated code from both projects but up to date.

## Table of Content

- [Intallation](#intallation)
- [Usage](#usage)
- [Console Output](#console-output)
- [Test Results](#test-result)
- [Todo](#todo)
- [Credits](#credits)

## Installation


## Usage:

```python

    import HtmlTestRunner
    import unittest


    class TestStringMethods(unittest.TestCase):
        """ Example test for HtmlRunner. """

        def test_upper(self):
            self.assertEqual('foo'.upper(), 'FOO')

        def test_isupper(self):
            self.assertTrue('FOO'.isupper())
            self.assertFalse('Foo'.isupper())

        def test_split(self):
            s = 'hello world'
            self.assertEqual(s.split(), ['hello', 'world'])
            # check that s.split fails when the separator is not a string
            with self.assertRaises(TypeError):
                s.split(2)

        def test_error(self):
            """ This test should be marked as error one. """
            raise ValueError

        def test_fail(self):
            """ This test should fail. """
            self.assertEqual(1, 2)

        @unittest.skip("This is a skipped test.")
        def test_skip(self):
            """ This test should be skipped. """
            pass

    if __name__ == '__main__':
        unittest.main(testRunner=HtmlTestRunner.HTMLTestRunner(output='example_dir'))
```

As simple as import the class an initialize it, it only have one request parameter that is output, this one is use to place the report in a sub direcotry in ``reports`` directory.


## Console output:

![Console output](docs/console_output.png)

This is what you got in the console.


## Test Result:

![Test Results](docs/test_results.gif)

This is a sample of the template that came by default with the runner. If you want
to customize it or use a new one just replace the template in the template folder,
the runner use jinja to render the template, so take in account the vars that are
being pass to the template.



## TODO

- [ ] Add Test
- [ ] Improve documentation
- [ ] Add custom templates
- [ ] Add xml results

## Credits

This package was created with Cookiecutter and the `audreyr/cookiecutter-pypackage` project template.

- [Cookiecutter](https://github.com/audreyr/cookiecutter)
- [audreyr/cookiecutter-pypackage](https://github.com/audreyr/cookiecutter-pypackage)

