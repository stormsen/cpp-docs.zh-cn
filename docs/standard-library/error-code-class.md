---
title: error_code 类 | Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- system_error/std::error_code
- system_error/std::error_code::value_type
- system_error/std::error_code::assign
- system_error/std::error_code::category
- system_error/std::error_code::clear
- system_error/std::error_code::default_error_condition
- system_error/std::error_code::message
- system_error/std::error_code::operator bool
dev_langs:
- C++
helpviewer_keywords:
- std::error_code
- std::error_code::value_type
- std::error_code::assign
- std::error_code::category
- std::error_code::clear
- std::error_code::default_error_condition
- std::error_code::message
ms.assetid: c09b4a96-cb14-4281-a319-63543f9b2b4a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b454a86957911060e33c82e79832e107313e0300
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2018
ms.locfileid: "45703594"
---
# <a name="errorcode-class"></a>error_code 类

表示特定于实现的低级别系统错误。

## <a name="syntax"></a>语法

```cpp
class error_code;
```

## <a name="remarks"></a>备注

`error_code` 类类型的对象存储错误代码值和指向对象的指针，该对象表示描述所报告的低级别系统错误的错误代码[类别](../standard-library/error-category-class.md)。

### <a name="constructors"></a>构造函数

|构造函数|描述|
|-|-|
|[error_code](#error_code)|构造 `error_code` 类型的对象。|

### <a name="typedefs"></a>Typedef

|类型名称|描述|
|-|-|
|[value_type](#value_type)|表示存储的错误代码值的类型。|

### <a name="member-functions"></a>成员函数

|成员函数|描述|
|-|-|
|[assign](#assign)|向错误代码分配错误代码值和类别。|
|[category](#category)|返回错误类别。|
|[clear](#clear)|清除错误代码值和类别。|
|[default_error_condition](#default_error_condition)|返回默认的错误条件。|
|[message](#message)|返回错误代码的名称。|

### <a name="operators"></a>运算符

|运算符|描述|
|-|-|
|[operator==](#op_eq_eq)|测试各 `error_code` 对象是否相等。|
|[operator!=](#op_neq)|测试各 `error_code` 对象是否不相等。|
|[operator<](#op_lt)|测试 `error_code` 对象是否小于要比较的传入对象 `error_code`。|
|[operator=](#op_eq)|向 `error_code` 对象分配新的枚举值。|
|[operator bool](#op_bool)|转换 `error_code` 类型的变量。|

## <a name="requirements"></a>要求

**标头：** \<system_error>

**命名空间：** std

## <a name="assign"></a>  error_code::assign

向错误代码分配错误代码值和类别。

```cpp
void assign(value_type val, const error_category& _Cat);
```

### <a name="parameters"></a>参数

|参数|描述|
|---------------|-----------------|
|*val*|要存储在 `error_code` 中的错误代码值。|
|*则*|要存储在 `error_code` 中的错误类别。|

### <a name="remarks"></a>备注

此成员函数存储*val*作为错误代码值和指向*则*。

## <a name="category"></a>  error_code::category

返回错误类别。

```cpp
const error_category& category() const;
```

### <a name="remarks"></a>备注

## <a name="clear"></a>  error_code::clear

清除错误代码值和类别。

```cpp
clear();
```

### <a name="remarks"></a>备注

此成员函数存储零错误代码值和指向 [generic_category](../standard-library/system-error-functions.md#generic_category) 对象的指针。

## <a name="default_error_condition"></a>  error_code::default_error_condition

返回默认的错误条件。

```cpp
error_condition default_error_condition() const;
```

### <a name="return-value"></a>返回值

[default_error_condition](../standard-library/error-category-class.md#default_error_condition) 指定的 [error_condition](../standard-library/error-condition-class.md)。

### <a name="remarks"></a>备注

此成员函数返回 `category().default_error_condition(value())`。

## <a name="error_code"></a>  error_code::error_code

构造 `error_code` 类型的对象。

```cpp
error_code();

error_code(value_type val, const error_category& _Cat);

template <class _Enum>
error_code(_Enum _Errcode,
    typename enable_if<is_error_code_enum<_Enum>::value,
    error_code>::type* = 0);
```

### <a name="parameters"></a>参数

|参数|描述|
|---------------|-----------------|
|*val*|要存储在 `error_code` 中的错误代码值。|
|*则*|要存储在 `error_code` 中的错误类别。|
|*_Errcode*|要存储在 `error_code` 中的枚举值。|

### <a name="remarks"></a>备注

第一个构造函数存储零错误代码值和指向 [generic_category](../standard-library/system-error-functions.md#generic_category) 的指针。

第二个构造函数存储*val*作为错误代码值和指向[error_category](../standard-library/error-category-class.md)。

第三个构造函数存储 `(value_type)_Errcode` 作为错误代码值和指向 [generic_category](../standard-library/system-error-functions.md#generic_category) 的指针。

## <a name="message"></a>  error_code::message

返回错误代码的名称。

```cpp
string message() const;
```

### <a name="return-value"></a>返回值

表示错误代码名称的 `string`。

### <a name="remarks"></a>备注

此成员函数返回 `category().message(value())`。

## <a name="op_eq_eq"></a>  error_code::operator==

测试各 `error_code` 对象是否相等。

```cpp
bool operator==(const error_code& right) const;
```

### <a name="parameters"></a>参数

|参数|描述|
|---------------|-----------------|
|*right*|要测试是否相等的对象。|

### <a name="return-value"></a>返回值

如果对象相等，则为 **true**；如果对象不相等，则为 **false**。

### <a name="remarks"></a>备注

该成员运算符将返回 `category() == right.category() && value == right.value()`。

## <a name="op_neq"></a>  error_code::operator!=

测试各 `error_code` 对象是否不相等。

```cpp
bool operator!=(const error_code& right) const;
```

### <a name="parameters"></a>参数

|参数|描述|
|---------------|-----------------|
|*right*|要测试是否不相等的对象。|

### <a name="return-value"></a>返回值

**true**如果`error_code`对象是否不等于`error_code`传入的对象*右*; 否则为**false**。

### <a name="remarks"></a>备注

该成员运算符将返回 `!(*this == right)`。

## <a name="op_lt"></a>  error_code::operator&lt;

测试 `error_code` 对象是否小于要比较的传入对象 `error_code`。

```cpp
bool operator<(const error_code& right) const;
```

### <a name="parameters"></a>参数

|参数|描述|
|---------------|-----------------|
|*right*|要比较的 error_code 对象。|

### <a name="return-value"></a>返回值

如果 `error_code` 对象小于要比较的传入对象 `error_code`，则为 **true**；否则为 **false**。

### <a name="remarks"></a>备注

该成员运算符将返回 `category() < right.category() || category() == right.category() && value < right.value()`。

## <a name="op_eq"></a>  error_code::operator=

向 `error_code` 对象分配新的枚举值。

```cpp
template <class _Enum>
typename enable_if<is_error_code_enum<_Enum>::value, error_code>::type&
    operator=(_Enum _Errcode);
```

### <a name="parameters"></a>参数

|参数|描述|
|---------------|-----------------|
|*_Errcode*|要向 `error_code` 对象分配的枚举值。|

### <a name="return-value"></a>返回值

对正在通过成员函数向其分配新枚举值的 `error_code` 对象的引用。

### <a name="remarks"></a>备注

成员运算符存储 `(value_type)_Errcode` 作为错误代码值和指向 [generic_category](../standard-library/system-error-functions.md#generic_category) 的指针。 它将返回 `*this`。

## <a name="op_bool"></a>  error_code::operator bool

转换 `error_code` 类型的变量。

```cpp
explicit operator bool() const;
```

### <a name="return-value"></a>返回值

`error_code` 对象的布尔值。

### <a name="remarks"></a>备注

该运算符将返回一个值可转换为 **，则返回 true**仅当[值](#value)不等于零。 返回类型是转换仅为**bool**不为`void *`或其他已知的标量类型。

## <a name="value"></a>  error_code::value

返回存储的错误代码值。

```cpp
value_type value() const;
```

### <a name="return-value"></a>返回值

[value_type](#value_type) 类型的已存储错误代码值。

### <a name="remarks"></a>备注

## <a name="value_type"></a>  error_code::value_type

表示存储的错误代码值的类型。

```cpp
typedef int value_type;
```

### <a name="remarks"></a>备注

此类型定义是的同义词**int**。

## <a name="see-also"></a>请参阅

[error_category 类](../standard-library/error-category-class.md)<br/>
[<system_error>](../standard-library/system-error.md)<br/>
