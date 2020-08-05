[TOC]



# QJsonDocument Class

QJsonDocument类提供了一种读取和写入JSON文档的方法。

| 属性     | 方法                     |
| -------- | ------------------------ |
| 头文件： | #include <QJsonDocument> |
| qmake:   | QT += core               |
| 从：     | Qt 5.0                   |

该类在Qt 5.0中引入。

 **注意：**此类中的所有函数都是[reentent](https://doc.qt.io/qt-5/threads-reentrancy.html)。

## 公开类型

| 类型 |                                                              |
| ---- | ------------------------------------------------------------ |
| enum | **[DataValidation](https://doc.qt.io/qt-5/qjsondocument.html#DataValidation-enum)** { Validate, BypassValidation } |
| enum | **[JsonFormat](https://doc.qt.io/qt-5/qjsondocument.html#JsonFormat-enum)** { Indented, Compact } |



## 公共成员函数

| 类型             | 函数名                                                       |
| ---------------- | ------------------------------------------------------------ |
|                  | **[QJsonDocument](https://doc.qt.io/qt-5/qjsondocument.html#QJsonDocument-4)**(QJsonDocument &&*other*) |
|                  | **[QJsonDocument](https://doc.qt.io/qt-5/qjsondocument.html#QJsonDocument-3)**(const QJsonDocument &*other*) |
|                  | [QJsonDocument](qjsondocument.html#QJsonDocument-2)(const QJsonArray &*array*) |
|                  | [QJsonDocument](qjsondocument.html#QJsonDocument-3)(const QJsonDocument &*other*) |
|                  | [QJsonDocument](qjsondocument.html#QJsonDocument-4)(QJsonDocument &&*other*) |
|                  | [~QJsonDocument](qjsondocument.html#dtor.QJsonDocument)()    |
| QJsonArray       | [array](qjsondocument.html#array)() const                    |
| bool             | [isArray](qjsondocument.html#isArray)() const                |
| bool             | [isEmpty](qjsondocument.html#isEmpty)() const                |
| bool             | [isNull](qjsondocument.html#isNull)() const                  |
| bool             | [isObject](qjsondocument.html#isObject)() const              |
| QJsonObject      | [object](qjsondocument.html#object)() const                  |
| const char *     | [rawData](qjsondocument.html#rawData)(int **size*) const     |
| void             | [setArray](qjsondocument.html#setArray)(const QJsonArray &*array*) |
| void             | [setObject](qjsondocument.html#setObject)(const QJsonObject &*object*) |
| void             | [swap](qjsondocument.html#swap)(QJsonDocument &*other*)      |
| QByteArray       | [toBinaryData](qjsondocument.html#toBinaryData)() const      |
| QByteArray       | [toJson](qjsondocument.html#toJson)() const                  |
| QVariant         | [toVariant](qjsondocument.html#toVariant)() const            |
| bool             | [operator!=](qjsondocument.html#operator-not-eq)(const QJsonDocument &*other*) const |
| QJsonDocument &  | [operator=](qjsondocument.html#operator-eq)(const QJsonDocument &*other*) |
| QJsonDocument &  | [operator=](qjsondocument.html#operator-eq-1)(QJsonDocument &&*other*) |
| bool             | [operator==](qjsondocument.html#operator-eq-eq)(const QJsonDocument &*other*) const |
| const QJsonValue | [operator[]](qjsondocument.html#operator-5b-5d)(const QString &*key*) const |
| const QJsonValue | [operator[]](qjsondocument.html#operator-5b-5d-1)(QLatin1String *key*) const |
| const QJsonValue | [operator[]](qjsondocument.html#operator-5b-5d-2)(int *i*) const |

## 静态成员函数

| 类型          | 函数名                                                       |
| ------------- | ------------------------------------------------------------ |
| QJsonDocument | [fromJson](qjsondocument.html#fromJson)(const QByteArray &*json*, QJsonParseError **error* = nullptr) |
| QJsonDocument | **[fromVariant](https://doc.qt.io/qt-5/qjsondocument.html#fromVariant)**（const QVariant＆ *variant*） |


## 详细说明

QJsonDocument是包装完整的JSON文档的类，可以从基于UTF-8编码的文本表示形式以及Qt自己的二进制格式读取和写入此文档。

可以使用[QJsonDocument :: fromJson](https://doc.qt.io/qt-5/qjsondocument.html#fromJson)（）将JSON文档从其基于文本的表示形式转换为QJsonDocument 。[toJson](https://doc.qt.io/qt-5/qjsondocument.html#toJson)（）将其转换回文本。解析器非常快速高效，并且将JSON转换为Qt使用的二进制表示形式。

可以使用[isNull](https://doc.qt.io/qt-5/qjsondocument.html#isNull)（）来查询已解析文档的有效性。

使用[isArray](https://doc.qt.io/qt-5/qjsondocument.html#isArray)（）和[isObject](https://doc.qt.io/qt-5/qjsondocument.html#isObject)（）可以查询文档是否包含数组或对象。可以使用[array](https://doc.qt.io/qt-5/qjsondocument.html#array)（）或[object](https://doc.qt.io/qt-5/qjsondocument.html#object)（）检索文档中包含的数组或对象，然后对其进行读取或操作。

也可以使用fromBinaryData（）或fromRawData（）从存储的二进制表示形式创建文档。

**另请参阅**[Qt中的JSON支持](https://doc.qt.io/qt-5/json.html)和[JSON保存游戏示例](https://doc.qt.io/qt-5/qtcore-serialization-savegame-example.html)。

## 成员类型文档

### enum QJsonDocument::DataValidation

当使用fromBinaryData() 或fromRawData() 转换为[QJsonDocument](https://doc.qt.io/qt-5/qjsondocument.html)时，此值用于告诉[QJsonDocument](https://doc.qt.io/qt-5/qjsondocument.html)是否验证二进制数据。

| 不变量                          | 值   | 描述                                                         |
| ------------------------------- | ---- | ------------------------------------------------------------ |
| QJsonDocument::Validate         | 0    | 在使用前验证数据。这是默认值。                               |
| QJsonDocument::BypassValidation | 1    | 绕过数据验证。仅当您从受信任的地方收到数据并知道其有效时才使用，因为使用无效数据可能会使应用程序崩溃。 |

### enum QJsonDocument::JsonFormat

此值定义使用[toJson](https://doc.qt.io/qt-5/qjsondocument.html#toJson)（）转换为[QJsonDocument](https://doc.qt.io/qt-5/qjsondocument.html)时生成的JSON字节数组的格式。

| 不变量                  | 值   | 描述                           |
| ----------------------- | ---- | ------------------------------ |
| QJsonDocument::Indented | 0    |<div style="height: 150pt"></div> |
| QJsonDocument::Compact  | 1    | 定义紧凑的输出，如下所示：     |

这个枚举是在Qt 5.1中引入或修改的。



## 成员函数文档

### QJsonDocument::QJsonDocument([QJsonDocument](https://doc.qt.io/qt-5/qjsondocument.html#QJsonDocument) &&*other*)

从other移动构造一个QJsonDocument。

### QJsonDocument::QJsonDocument(const [QJsonDocument](https://doc.qt.io/qt-5/qjsondocument.html#QJsonDocument) &*other*)

创建另一个文档的副本。

### QJsonDocument::QJsonDocument(const [QJsonArray](https://doc.qt.io/qt-5/qjsonarray.html) &*array*)

从array构造一个QJsonDocument。

### QJsonDocument::QJsonDocument(const [QJsonObject](https://doc.qt.io/qt-5/qjsonobject.html) &*object*)

从object中创建一个QJsonDocument。

### QJsonDocument::QJsonDocument()

构造一个空的无效文档。

### [QJsonDocument](https://doc.qt.io/qt-5/qjsondocument.html#QJsonDocument) &QJsonDocument::operator=([QJsonDocument](https://doc.qt.io/qt-5/qjsondocument.html#QJsonDocument) &&*other*)

将otherr移动到该文档。

Qt5.10引入了该功能。

### [QJsonDocument](https://doc.qt.io/qt-5/qjsondocument.html#QJsonDocument) &QJsonDocument::operator=(const [QJsonDocument](https://doc.qt.io/qt-5/qjsondocument.html#QJsonDocument) &*other*)

将另一个文档分配给QJsonDocument。返回此对象的引用。

### QJsonDocument::~QJsonDocument()

删除该文档。

使用fromRawData设置的二进制数据不会被释放。

### [QJsonArray](https://doc.qt.io/qt-5/qjsonarray.html) QJsonDocument::array() const

返回文档中包含的QJsonArray。

如果文档包含对象，则返回一个空数组。

**另请参见**[isArray](https://doc.qt.io/qt-5/qjsondocument.html#isArray)（），[object](https://doc.qt.io/qt-5/qjsondocument.html#object)（）和[setArray](https://doc.qt.io/qt-5/qjsondocument.html#setArray)（）。

### [QJsonDocument](https://doc.qt.io/qt-5/qjsondocument.html#QJsonDocument) QJsonDocument::fromJson(const [QByteArray](https://doc.qt.io/qt-5/qbytearray.html) &*json*, [QJsonParseError](https://doc.qt.io/qt-5/qjsonparseerror.html) **error* = nullptr)	[static]

将*json*解析为UTF-8编码的JSON文档，并[从中](https://doc.qt.io/qt-5/qjsondocument.html)创建[QJsonDocument](https://doc.qt.io/qt-5/qjsondocument.html)。

如果解析成功，则返回有效的（非空）[QJsonDocument](https://doc.qt.io/qt-5/qjsondocument.html)。如果失败，则返回的文档将为null，并且可选的*error*变量将包含有关该错误的更多详细信息。

**另请参见**[toJson](https://doc.qt.io/qt-5/qjsondocument.html#toJson)（），[QJsonParseError](https://doc.qt.io/qt-5/qjsonparseerror.html)和[isNull](https://doc.qt.io/qt-5/qjsondocument.html#isNull)（）。

### [QJsonDocument](https://doc.qt.io/qt-5/qjsondocument.html#QJsonDocument) QJsonDocument::fromVariant(const [QVariant](https://doc.qt.io/qt-5/qvariant.html) &*variant*)	[static]

从[QVariant ](https://doc.qt.io/qt-5/qvariant.html)*变体*创建[QJsonDocument](https://doc.qt.io/qt-5/qjsondocument.html)。

如果*变量*包含[QVariantMap](https://doc.qt.io/qt-5/qvariant.html#QVariantMap-typedef)，[QVariantHash](https://doc.qt.io/qt-5/qvariant.html#QVariantHash-typedef)，[QVariantList](https://doc.qt.io/qt-5/qvariant.html#QVariantList-typedef)或[QStringList](https://doc.qt.io/qt-5/qstringlist.html)以外的任何其他类型，则返回的文档无效。

**另请参见**[toVariant](https://doc.qt.io/qt-5/qjsondocument.html#toVariant)（）。

### bool QJsonDocument::isArray() const

返回`true`文档是否包含数组。

**另请参见**[array](https://doc.qt.io/qt-5/qjsondocument.html#array)（）和[isObject](https://doc.qt.io/qt-5/qjsondocument.html#isObject)（）。

### bool QJsonDocument::isEmpty() const

如果返回true, 则该文档不包含任何数据。

### bool QJsonDocument::isNull() const

如果返回true，则空文档是通过默认构造函数创建的文档。

从UTF-8编码的文本或二进制格式创建的文档在解析期间内得到验证。如果验证失败了，也是返回true。

### bool QJsonDocument::isObject() const

返回true 代表文档包含对象。

**另请参见**[object](https://doc.qt.io/qt-5/qjsondocument.html#object)（）和[isArray](https://doc.qt.io/qt-5/qjsondocument.html#isArray)（）。

### [QJsonObject](https://doc.qt.io/qt-5/qjsonobject.html) QJsonDocument::object() const

返回文档中包含的[QJsonObject](https://doc.qt.io/qt-5/qjsonobject.html)。

如果文档包含数组，则返回一个空对象。

**另请参见**[isObject](https://doc.qt.io/qt-5/qjsondocument.html#isObject)（），[array](https://doc.qt.io/qt-5/qjsondocument.html#array)（）和[setObject](https://doc.qt.io/qt-5/qjsondocument.html#setObject)（）。

### void QJsonDocument::setArray(const [QJsonArray](https://doc.qt.io/qt-5/qjsonarray.html) &*array*)

将*数组*设置为本文档的主要对象。

**另请参见**[setObject](https://doc.qt.io/qt-5/qjsondocument.html#setObject)（）和[array](https://doc.qt.io/qt-5/qjsondocument.html#array)（）。

### void QJsonDocument::setObject(const [QJsonObject](https://doc.qt.io/qt-5/qjsonobject.html) &*object*)

设置*对象*本文件的主要对象。

**另请参见**[setArray](https://doc.qt.io/qt-5/qjsondocument.html#setArray)（）和[object](https://doc.qt.io/qt-5/qjsondocument.html#object)（）。

### void QJsonDocument::swap([QJsonDocument](https://doc.qt.io/qt-5/qjsondocument.html#QJsonDocument) &*other*)

与此交换*其他*文件。此操作非常快，并且永远不会失败。

Qt 5.10中引入了此功能。

### [QByteArray](https://doc.qt.io/qt-5/qbytearray.html) QJsonDocument::toJson() const

将[QJsonDocument](https://doc.qt.io/qt-5/qjsondocument.html)转换为缩进的，UTF-8编码的JSON文档。

**另请参见**[fromJson](https://doc.qt.io/qt-5/qjsondocument.html#fromJson)（）。

### [QByteArray](https://doc.qt.io/qt-5/qbytearray.html) QJsonDocument::toJson([QJsonDocument::JsonFormat](https://doc.qt.io/qt-5/qjsondocument.html#JsonFormat-enum) *format*) const

将[QJsonDocument](https://doc.qt.io/qt-5/qjsondocument.html)转换为提供*格式*的UTF-8编码的JSON文档。

此功能在Qt 5.1中引入。

**另请参见**[fromJson](https://doc.qt.io/qt-5/qjsondocument.html#fromJson)（）和[JsonFormat](https://doc.qt.io/qt-5/qjsondocument.html#JsonFormat-enum)。

### [QVariant](https://doc.qt.io/qt-5/qvariant.html) QJsonDocument::toVariant() const

返回表示Json文档的[QVariant](https://doc.qt.io/qt-5/qvariant.html)。

返回的变型将是一个[QVariantList](https://doc.qt.io/qt-5/qvariant.html#QVariantList-typedef)如果该文件是一个[QJsonArray](https://doc.qt.io/qt-5/qjsonarray.html)和[QVariantMap](https://doc.qt.io/qt-5/qvariant.html#QVariantMap-typedef)如果该文件是一个[QJsonObject](https://doc.qt.io/qt-5/qjsonobject.html)。

**另请参见**[fromVariant](https://doc.qt.io/qt-5/qjsondocument.html#fromVariant)（）和[QJsonValue :: toVariant](https://doc.qt.io/qt-5/qjsonvalue.html#toVariant)（）。

### bool QJsonDocument::operator!=(const [QJsonDocument](https://doc.qt.io/qt-5/qjsondocument.html#QJsonDocument) &*other*) const

返回true代表other不等于该文档。

### bool QJsonDocument::operator==(const [QJsonDocument](https://doc.qt.io/qt-5/qjsondocument.html#QJsonDocument) &*other*) const

返回true代表other等于该文档。

### const [QJsonValue](https://doc.qt.io/qt-5/qjsonvalue.html) QJsonDocument::operator[](const [QString](https://doc.qt.io/qt-5/qstring.html) &*key*) const

返回表示键*key*的值的[QJsonValue](https://doc.qt.io/qt-5/qjsonvalue.html)。

等效于调用[对象](https://doc.qt.io/qt-5/qjsondocument.html#object)（）.value（key）。

如果键不存在，或者[isObject](https://doc.qt.io/qt-5/qjsondocument.html#isObject)（）为false ，则返回的[QJsonValue](https://doc.qt.io/qt-5/qjsonvalue.html)为[QJsonValue :: Undefined](https://doc.qt.io/qt-5/qjsonvalue.html#Type-enum)。

Qt 5.10中引入了此功能。

**另请参见**[QJsonValue](https://doc.qt.io/qt-5/qjsonvalue.html)，[QJsonValue :: isUndefined](https://doc.qt.io/qt-5/qjsonvalue.html#isUndefined)（）和[QJsonObject](https://doc.qt.io/qt-5/qjsonobject.html)。

### const [QJsonValue](https://doc.qt.io/qt-5/qjsonvalue.html) QJsonDocument::operator[]([QStringView](https://doc.qt.io/qt-5/qstringview.html) *key*) const

这是一个重载功能。

Qt 5.14中引入了此功能。

### const [QJsonValue](https://doc.qt.io/qt-5/qjsonvalue.html) QJsonDocument::operator[]([QLatin1String](https://doc.qt.io/qt-5/qlatin1string.html) *key*) const

这是一个过载功能。

Qt 5.10中引入了此功能。

### const [QJsonValue](https://doc.qt.io/qt-5/qjsonvalue.html) QJsonDocument::operator[](int *i*) const

返回表示索引*i*的值的[QJsonValue](https://doc.qt.io/qt-5/qjsonvalue.html)。

等效于调用[array](https://doc.qt.io/qt-5/qjsondocument.html#array)（）.at（i）。

如果*我*超出范围，或者[isArray](https://doc.qt.io/qt-5/qjsondocument.html#isArray)（）为false ，则返回的[QJsonValue](https://doc.qt.io/qt-5/qjsonvalue.html)为[QJsonValue :: Undefined](https://doc.qt.io/qt-5/qjsonvalue.html#Type-enum)。

Qt 5.10中引入了此功能。

**另请参见**[QJsonValue](https://doc.qt.io/qt-5/qjsonvalue.html)，[QJsonValue :: isUndefined](https://doc.qt.io/qt-5/qjsonvalue.html#isUndefined)（）和[QJsonArray](https://doc.qt.io/qt-5/qjsonarray.html)。

