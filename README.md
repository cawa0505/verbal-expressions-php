# Verbal Expressions-PHP
- Forked from the original [PHP Verbal Expressions](https://github.com/VerbalExpressions/PHPVerbalExpressions) library.
- Ported from [VerbalExpressions](https://github.com/VerbalExpressions/JSVerbalExpressions).

Verbal Expressions is a PHP library that helps to construct hard regular expressions.

## Examples
```php

$regex = new VerbalExpressions;

$regex->startOfLine()
    ->then("http")
    ->maybe("s")
    ->then("://")
    ->maybe("www.")
    ->anythingBut(" ")
    ->endOfLine();

if ($regex->test("https://github.com/")) {
    echo "valid url";
} else {
    echo "invalid url";
}

if (preg_match($regex, 'http://github.com')) {
    echo 'valid url';
} else {
    echo 'invalid url';
}

echo "<pre>". $regex->getRegex() ."</pre>";

echo $regex->clean(array("modifiers" => "m", "replaceLimit" => 4))
    ->find(' ')
    ->replace("This is a small test http://somesite.com and some more text.", "-");
```

## Other Implementations
You can see an up to date list of all ports on [VerbalExpressions.github.io](http://VerbalExpressions.github.io).

- [Javascript](https://github.com/jehna/VerbalExpressions)
- [Ruby](https://github.com/VerbalExpressions/RubyVerbalExpressions)
- [C#](https://github.com/VerbalExpressions/CSharpVerbalExpressions)
- [Python](https://github.com/VerbalExpressions/PythonVerbalExpressions)
- [Java](https://github.com/VerbalExpressions/JavaVerbalExpressions)
- [C++](https://github.com/VerbalExpressions/CppVerbalExpressions)

## Building the project and running the tests
All tests are written using PHPUnit. Please ensure that you have it installed and run all tests before contributing.
