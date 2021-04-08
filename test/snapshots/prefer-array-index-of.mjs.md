# Snapshot report for `test/prefer-array-index-of.mjs`

The actual snapshot is saved in `prefer-array-index-of.mjs.snap`.

Generated by [AVA](https://avajs.dev).

## Invalid #1
      1 | values.findIndex(x => x === "foo")

> Output

    `␊
      1 | values.indexOf("foo")␊
    `

> Error 1/1

    `␊
    > 1 | values.findIndex(x => x === "foo")␊
        |        ^^^^^^^^^ Use \`.indexOf()\` instead of \`.findIndex()\` when looking for the index of an item.␊
    `

## Invalid #2
      1 | values.findIndex(x => "foo" === x)

> Output

    `␊
      1 | values.indexOf("foo")␊
    `

> Error 1/1

    `␊
    > 1 | values.findIndex(x => "foo" === x)␊
        |        ^^^^^^^^^ Use \`.indexOf()\` instead of \`.findIndex()\` when looking for the index of an item.␊
    `

## Invalid #3
      1 | values.findIndex(x => {return x === "foo";})

> Output

    `␊
      1 | values.indexOf("foo")␊
    `

> Error 1/1

    `␊
    > 1 | values.findIndex(x => {return x === "foo";})␊
        |        ^^^^^^^^^ Use \`.indexOf()\` instead of \`.findIndex()\` when looking for the index of an item.␊
    `

## Invalid #4
      1 | values.findIndex(function (x) {return x === "foo";})

> Output

    `␊
      1 | values.indexOf("foo")␊
    `

> Error 1/1

    `␊
    > 1 | values.findIndex(function (x) {return x === "foo";})␊
        |        ^^^^^^^^^ Use \`.indexOf()\` instead of \`.findIndex()\` when looking for the index of an item.␊
    `

## Invalid #5
      1 | // 1
      2 | (0, values)
      3 | 	// 2
      4 | 	./* 3 */findIndex /* 3 */ (
      5 | 		/* 4 */
      6 | 		x /* 5 */ => /* 6 */ x /* 7 */ === /* 8 */ "foo" /* 9 */
      7 | 	) /* 10 */

> Output

    `␊
      1 | // 1␊
      2 | (0, values)␊
      3 | 	// 2␊
      4 | 	./* 3 */indexOf /* 3 */ (␊
      5 | 		/* 4 */␊
      6 | 		"foo" /* 9 */␊
      7 | 	) /* 10 */␊
    `

> Error 1/1

    `␊
      1 | // 1␊
      2 | (0, values)␊
      3 | 	// 2␊
    > 4 | 	./* 3 */findIndex /* 3 */ (␊
        | 	        ^^^^^^^^^ Use \`.indexOf()\` instead of \`.findIndex()\` when looking for the index of an item.␊
      5 | 		/* 4 */␊
      6 | 		x /* 5 */ => /* 6 */ x /* 7 */ === /* 8 */ "foo" /* 9 */␊
      7 | 	) /* 10 */␊
    `

## Invalid #6
      1 | foo.findIndex(function (element) {
      2 | 	return element === bar.findIndex(x => x === 1);
      3 | });

> Output

    `␊
      1 | foo.findIndex(function (element) {␊
      2 | 	return element === bar.indexOf(1);␊
      3 | });␊
    `

> Error 1/2

    `␊
    > 1 | foo.findIndex(function (element) {␊
        |     ^^^^^^^^^ Use \`.indexOf()\` instead of \`.findIndex()\` when looking for the index of an item.␊
      2 | 	return element === bar.findIndex(x => x === 1);␊
      3 | });␊
    ␊
    --------------------------------------------------------------------------------␊
    Suggestion 1/1: Replace \`.findIndex()\` with \`.indexOf()\`.␊
      1 | foo.indexOf(bar.findIndex(x => x === 1));␊
    `

> Error 2/2

    `␊
      1 | foo.findIndex(function (element) {␊
    > 2 | 	return element === bar.findIndex(x => x === 1);␊
        | 	                       ^^^^^^^^^ Use \`.indexOf()\` instead of \`.findIndex()\` when looking for the index of an item.␊
      3 | });␊
    `

## Invalid #7
      1 | values.findIndex(x => x === (0, "foo"))

> Output

    `␊
      1 | values.indexOf((0, "foo"))␊
    `

> Error 1/1

    `␊
    > 1 | values.findIndex(x => x === (0, "foo"))␊
        |        ^^^^^^^^^ Use \`.indexOf()\` instead of \`.findIndex()\` when looking for the index of an item.␊
    `

## Invalid #8
      1 | values.findIndex((x => x === (0, "foo")))

> Output

    `␊
      1 | values.indexOf((0, "foo"))␊
    `

> Error 1/1

    `␊
    > 1 | values.findIndex((x => x === (0, "foo")))␊
        |        ^^^^^^^^^ Use \`.indexOf()\` instead of \`.findIndex()\` when looking for the index of an item.␊
    `

## Invalid #9
      1 | function fn() {
      2 | 	foo.findIndex(x => x === arguments.length)
      3 | }

> Output

    `␊
      1 | function fn() {␊
      2 | 	foo.indexOf(arguments.length)␊
      3 | }␊
    `

> Error 1/1

    `␊
      1 | function fn() {␊
    > 2 | 	foo.findIndex(x => x === arguments.length)␊
        | 	    ^^^^^^^^^ Use \`.indexOf()\` instead of \`.findIndex()\` when looking for the index of an item.␊
      3 | }␊
    `

## Invalid #10
      1 | function fn() {
      2 | 	foo.findIndex(x => x === this[1])
      3 | }

> Output

    `␊
      1 | function fn() {␊
      2 | 	foo.indexOf(this[1])␊
      3 | }␊
    `

> Error 1/1

    `␊
      1 | function fn() {␊
    > 2 | 	foo.findIndex(x => x === this[1])␊
        | 	    ^^^^^^^^^ Use \`.indexOf()\` instead of \`.findIndex()\` when looking for the index of an item.␊
      3 | }␊
    `

## Invalid #11
      1 | values.findIndex(x => x === foo())

> Error 1/1

    `␊
    > 1 | values.findIndex(x => x === foo())␊
        |        ^^^^^^^^^ Use \`.indexOf()\` instead of \`.findIndex()\` when looking for the index of an item.␊
    ␊
    --------------------------------------------------------------------------------␊
    Suggestion 1/1: Replace \`.findIndex()\` with \`.indexOf()\`.␊
      1 | values.indexOf(foo())␊
    `

## Invalid #12
      1 | foo.findIndex(function a(x) {
      2 | 	return x === (function (a) {
      3 | 		return a(this) === arguments[1]
      4 | 	}).call(thisObject, anotherFunctionNamedA, secondArgument)
      5 | })

> Error 1/1

    `␊
    > 1 | foo.findIndex(function a(x) {␊
        |     ^^^^^^^^^ Use \`.indexOf()\` instead of \`.findIndex()\` when looking for the index of an item.␊
      2 | 	return x === (function (a) {␊
      3 | 		return a(this) === arguments[1]␊
      4 | 	}).call(thisObject, anotherFunctionNamedA, secondArgument)␊
      5 | })␊
    ␊
    --------------------------------------------------------------------------------␊
    Suggestion 1/1: Replace \`.findIndex()\` with \`.indexOf()\`.␊
      1 | foo.indexOf((function (a) {␊
      2 | 		return a(this) === arguments[1]␊
      3 | 	}).call(thisObject, anotherFunctionNamedA, secondArgument))␊
    `