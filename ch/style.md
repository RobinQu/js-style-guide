风格规范
===========

* 命名

	* 变量命名，驼背法: *Always*
	
	    **functionNamesLikeThis**, **variableNamesLikeThis**, **ClassNamesLikeThis**, **EnumNamesLikeThis**, **methodNamesLikeThis**, and **SYMBOLIC_CONSTANTS_LIKE_THIS**
	
	* 缩写和短语用在命名的时候不以全大写形式出现 *Preferred*
	
			getInnerHtml(), getXml(), XmlDocument
	
	* 使用带名称的闭包 *Preferred*

			req.on('end', function onEnd() {
			  console.log('winning');
			});

	* Boolean变量以“**is**”开头 *Preferred*

	* 初始化方法以"**init**"、"**initialize**"开头 *Preferred*

	* 集合的命名必须是单词的复数形式 *Always*

	* 记录数量的变量应该以"**num**"或"**count**"开头 *Always*

	* 循环迭代变量应该以"**i**", "**j**", "**k**"依次命名 *Always*

* 使用2个空格作为一个单位的缩进 *Preferred*

* 以空格结尾 *Never*

* Getters *Preferred*

* Setters *Careful*

* 嵌套闭包 *Never*

		//wrong	
		setTimeout(function() {
		  client.connect(function() {
		    console.log('losing');
		  });
		}, 1000);

* 重要的判断条件，要单独创建一个变量

		var isAuthorized = (user.isAdmin() || user.isModerator());
		if (isAuthorized) {
		  console.log('winning');
		}

* 自定义的toString方法
  
    确保没有任何副作用
  
* 代码格式化
  
    * if语句的大括号: *Always*


            if (something) {
              // ...
            } else {
              // ...
            }


    * 数组和对象初始化: *Always*

            var arr = [1, 2, 3];  // No space after [ or before ].
            var obj = {a: 1, b: 2, c: 3};  // No space after { or before }.

    * 多行字面量以2个空格打头，并以逗号结尾: *Always*

            // Object initializer.
            var inset = {
              top: 10,
              right: 20,
              bottom: 15,
              left: 12
            };

            // Array initializer.
            this.rows_ = [
              '"Slartibartfast" <fjordmaster@magrathea.com>',
              '"Zaphod Beeblebrox" <theprez@universe.gov>',
              '"Ford Prefect" <ford@theguide.com>',
              '"Arthur Dent" <has.no.tea@gmail.com>',
              '"Marvin the Paranoid Android" <marv@googlemail.com>',
              'the.mice@magrathea.com'
            ];

    * 字面量键值名称无需对齐: *Preferred*

            CORRECT_Object.prototype = {
              a: 0,
              b: 1,
              lengthyName: 2
            };

    * 函数参数格式: *Preferred*

            // Four-space, wrap at 80.  Works with very long function names, survives
            // renaming without reindenting, low on space.
            goog.foo.bar.doThingThatIsVeryDifficultToExplain = function(
                veryDescriptiveArgumentNumberOne, veryDescriptiveArgumentTwo,
                tableModelEventHandlerProxy, artichokeDescriptorAdapterIterator) {
              // ...
            };

            // Four-space, one argument per line.  Works with long function names,
            // survives renaming, and emphasizes each argument.
            goog.foo.bar.doThingThatIsVeryDifficultToExplain = function(
                veryDescriptiveArgumentNumberOne,
                veryDescriptiveArgumentTwo,
                tableModelEventHandlerProxy,
                artichokeDescriptorAdapterIterator) {
              // ...
            };

            // Parenthesis-aligned indentation, wrap at 80.  Visually groups arguments,
            // low on space.
            function foo(veryDescriptiveArgumentNumberOne, veryDescriptiveArgumentTwo,
                         tableModelEventHandlerProxy, artichokeDescriptorAdapterIterator) {
              // ...
            }

            // Parenthesis-aligned, one argument per line.  Visually groups and
            // emphasizes each individual argument.
            function bar(veryDescriptiveArgumentNumberOne,
                         veryDescriptiveArgumentTwo,
                         tableModelEventHandlerProxy,
                         artichokeDescriptorAdapterIterator) {
              // ...
            }

            if (veryLongFunctionNameA(
                    veryLongArgumentName) ||
                veryLongFunctionNameB(
                veryLongArgumentName)) {
              veryLongFunctionNameC(veryLongFunctionNameD(
                  veryLongFunctioNameE(
                      veryLongFunctionNameF)));
            }

    * 传递匿名函数: *Preferred*

            prefix.something.reallyLongFunctionName('whatever', function(a1, a2) {
              if (a1.equals(a2)) {
                someOtherLongFunctionName(a1);
              } else {
                andNowForSomethingCompletelyDifferent(a2.parrot);
              }
            });

            var names = prefix.something.myExcellentMapFunction(
                verboselyNamedCollectionOfItems,
                function(item) {
                  return item.name;
                });
      
    * 使用更多的缩进: *Preferred*

            someWonderfulHtml = '' +
                                getEvenMoreHtml(someReallyInterestingValues, moreValues,
                                                evenMoreParams, 'a duck', true, 72,
                                                slightlyMoreMonkeys(0xfff)) +
                                '';

            thisIsAVeryLongVariableName =
                hereIsAnEvenLongerOtherFunctionNameThatWillNotFitOnPrevLine();

            thisIsAVeryLongVariableName = 'expressionPartOne' + someMethodThatIsLong() +
                thisIsAnEvenLongerOtherFunctionNameThatCannotBeIndentedMore();

            someValue = this.foo(
                shortArg,
                'Some really long string arg - this is a pretty common case, actually.',
                shorty2,
                this.bar());

            if (searchableCollection(allYourStuff).contains(theStuffYouWant) &&
                !ambientNotification.isActive() && (client.isAmbientSupported() ||
                                                    client.alwaysTryAmbientAnyways())) {
              ambientNotification.activate();
            }


    * 使用空行来将逻辑上相关的代码分组: *Preferred*

    * 二元和三元运算符: *Preferred*

            var x = a ? b : c;  // All on one line if it will fit.

            // Indentation +4 is OK.
            var y = a ?
                longButSimpleOperandB : longButSimpleOperandC;

            // Indenting to the line position of the first operand is also OK.
            var z = a ?
                    moreComplicatedB :
                    moreComplicatedC;
              
* 可见性 @private and @protected: *Preferred*

          // File 1.

          /** @constructor */  
          AA_PublicClass = function() {
          };

          /** @private */    
          AA_PublicClass.staticPrivateProp_ = 1;

          /** @private */
          AA_PublicClass.prototype.privateProp_ = 2;

          /** @protected */  
          AA_PublicClass.staticProtectedProp = 31;

          /** @protected */  
          AA_PublicClass.prototype.protectedProp = 4;

* 使用JSDoc: *Preferred*