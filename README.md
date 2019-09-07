# quality_assurance

静态代码检查工具，放到单独的repo，所有项目通过submodule方式引入

- [pmd](https://pmd.github.io/latest/index.html)
- [checkstyle](https://github.com/checkstyle/checkstyle)
- [findbugs](https://github.com/findbugsproject/findbugs)(升级jdk11后已无法使用，等其继承者spotbugs发布最新版即替换)

## 更新方式

新`clone`下来的后台项目是不会默认把`submodule`也`clone`下来的，所以需要在项目的根目录执行下面的命令

```shell
git submodule update --init --recursive
```

执行完之后，`quality_assurance`就会clone到本地项目目录下，如此即可正常使用了

后面如果`quality_assurance`有更新，执行同样的命令即可.

## PMD说明

所用版本为`6.16.0`，使用的规则有：

```text
AvoidStringBufferField
AvoidUsingHardCodedIP
CheckResultSet
ConstantsInInterface
DefaultLabelNotLastInSwitchStmt
DoubleBraceInitialization
ForLoopCanBeForeach
GuardLogStatement
LooseCoupling
OneDeclarationPerLine
PositionLiteralsFirstInCaseInsensitiveComparisons
PositionLiteralsFirstInComparisons
SwitchStmtsShouldHaveDefault
UnusedFormalParameter
UnusedImports
UnusedLocalVariable
UnusedPrivateField
UnusedPrivateMethod
UseAssertEqualsInsteadOfAssertTrue
UseAssertNullInsteadOfAssertTrue
UseAssertSameInsteadOfAssertTrue
UseAssertTrueInsteadOfAssertEquals
UseCollectionIsEmpty

<!-- NAMING CONVENTIONS -->
ClassNamingConventions 其中utilityClassPattern的值为"[A-Z][a-zA-Z0-9]+"


FormalParameterNamingConventions
GenericsNaming
LocalVariableNamingConventions
MethodNamingConventions
PackageCase


<!-- OTHER -->
AvoidDollarSigns
AvoidProtectedFieldInFinalClass
AvoidProtectedMethodInFinalClassNotExtending
ControlStatementBraces
DontImportJavaLang
DuplicateImports
ExtendsObject
ForLoopShouldBeWhileLoop
IdenticalCatchBranches
NoPackage
UnnecessaryConstructor
UnnecessaryFullyQualifiedName
UnnecessaryModifier
UnnecessaryReturn
UselessParentheses
UselessQualifiedThis


AbstractClassWithoutAnyMethod
ClassWithOnlyPrivateConstructorsShouldBeFinal
DoNotExtendJavaLangError
FinalFieldCouldBeStatic
LogicInversion
SimplifiedTernary
SimplifyBooleanReturns
SimplifyConditional
SingularField
UselessOverridingMethod
UseUtilityClass


UncommentedEmptyConstructor
UncommentedEmptyMethodBody

AssignmentInOperand 其中allowWhile的属性为true

AssignmentToNonFinalStatic
AvoidAccessibilityAlteration
AvoidBranchingStatementAsLastInLoop
AvoidCatchingThrowable
AvoidDecimalLiteralsInBigDecimalConstructor
AvoidInstanceofChecksInCatchClause
AvoidMultipleUnaryOperators
AvoidUsingOctalValues
BadComparison
BrokenNullCheck
CheckSkipResult
ClassCastExceptionWithToArray
CloneMethodMustBePublic
CloneMethodMustImplementCloneable
CloneMethodReturnTypeMustMatchClassName
CloneThrowsCloneNotSupportedException
CloseResource
CompareObjectsWithEquals
DoNotCallGarbageCollectionExplicitly
DoNotExtendJavaLangThrowable
DontUseFloatTypeForLoopIndices
EqualsNull
IdempotentOperations
ImportFromSamePackage
InstantiationToGetClass
JumbledIncrementer
MisplacedNullCheck
MissingBreakInSwitch
MissingStaticMethodInNonInstantiatableClass
NonCaseLabelInSwitchStatement
NonStaticInitializer
OverrideBothEqualsAndHashcode
ProperCloneImplementation
ProperLogger
ReturnEmptyArrayRatherThanNull
ReturnFromFinallyBlock
SingleMethodSingleton
SingletonClassReturningNewInstance
SuspiciousEqualsMethodName
SuspiciousHashcodeMethodName
SuspiciousOctalEscape
UnconditionalIfStatement
UnnecessaryConversionTemporary
UnusedNullCheckInEquals
UseEqualsToCompareStrings
UselessOperationOnImmutable
UseLocaleWithCaseConversions

<!-- Empty rules -->
EmptyCatchBlock
EmptyFinalizer
EmptyFinallyBlock
EmptyIfStmt
EmptyInitializer
EmptyStatementBlock
EmptyStatementNotInLoop
EmptySwitchStatements
EmptySynchronizedBlock
EmptyTryBlock
EmptyWhileStmt

AvoidThreadGroup
AvoidUsingVolatile
DontCallThreadRun
DoubleCheckedLocking
NonThreadSafeSingleton
UnsynchronizedStaticFormatter
UseNotifyAllInsteadOfNotify

BigIntegerInstantiation
BooleanInstantiation
OptimizableToArrayCall
```

修改或者移除规则，请同步更新

TODO：有空可以把上述规则的解释加上

## checkstyle

版本为`6.15.0`，关注点在：

- 注释
- 命名
- 换行

## findbugs(spotbugs)

TODO