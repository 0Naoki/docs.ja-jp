---
title: "概念モデル正規関数と SQL Server 関数とのマッピング"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a2631bc-a426-4c0a-ba8d-26d9c80d39e2
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: ad42c31353851f0846a484f7ab8bcb83c71d0e0b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="conceptual-model-canonical-to-sql-server-functions-mapping"></a>概念モデル正規関数と SQL Server 関数とのマッピング
このトピックでは、概念モデル正規関数を対応する SQL Server 関数にマップする方法について説明します。  
  
## <a name="date-and-time-functions"></a>日付と時刻関数  
 日付と時刻の関数のマッピングを次の表に示します。  
  
|正規関数|SQL Server 関数|  
|-------------------------|--------------------------|  
|[AddDays(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(day, number, date)`|  
|[AddHours(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(hour, number, date)`|  
|[AddMicroseconds(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(microsecond, number, date)`|  
|[AddMilliseconds(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(millisecond, number, date)`|  
|[AddMinutes(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(minute, number, date)`|  
|[AddMonths(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(month, number, date)`|  
|[AddNanoseconds(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(nanosecond, number, date)`|  
|[AddSeconds(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(second, number, date)`|  
|[AddYears(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(year, number, date)`|  
|[CreateDateTime (年、月、日、時、分、秒)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|SQL Server 2000 と SQL Server 2005 の場合、書式指定された `datetime` 値がサーバー上に作成されます。 SQL Server 2008 以上の場合、`datetime2` 値がサーバー上に作成されます。|  
|[CreateDateTimeOffset (年、月、日、時、分、秒、tzoffset)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|書式指定された `datetimeoffset` 値がサーバー上に作成されます。<br /><br /> SQL Server 2000 と SQL Server 2005 ではサポートされません。|  
|[CreateTime (時間、分、秒)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|書式指定された `time` 値がサーバー上に作成されます。<br /><br /> SQL Server 2000 と SQL Server 2005 ではサポートされません。|  
|[CurrentDateTime()](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`SysDateTime()` (SQL Server 2008)。<br /><br /> `GetDate()` (SQL Server 2000 および SQL Server 2005)。|  
|[CurrentDateTimeOffset()](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`SysDateTimeOffset()` (SQL Server 2008)。<br /><br /> SQL Server 2000 と SQL Server 2005 ではサポートされません。|  
|[CurrentUtcDateTime()](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`SysUtcDateTime()` (SQL Server 2008)。 `GetUtcDate()` (SQL Server 2000 および SQL Server 2005)。|  
|[DayOfYear(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(dayofyear, expression)`|  
|[Day(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(day, expression)`|  
|[DiffDays (startExpression、endExpression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(day, startdate, enddate)`|  
|[DiffHours (startExpression、endExpression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(hour, startdate, enddate)`|  
|[DiffMicroseconds (startExpression、endExpression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(microsecond, startdate, enddate)`|  
|[DiffMilliseconds (startExpression、endExpression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(millisecond, startdate, enddate)`|  
|[DiffMinutes (startExpression、endExpression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(minute, startdate, enddate)`|  
|[DiffNanoseconds (startExpression、endExpression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(nanosecond, startdate, enddate)`|  
|[DiffSeconds (startExpression、endExpression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(second, startdate, enddate)`|  
|[DiffYears (startExpression、endExpression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(year, startdate, enddate)`|  
|[GetTotalOffsetMinutes(DateTimeOffset)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(tzoffset, expression)`|  
|[Hour(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(hour, expression)`|  
|[Millisecond(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(millisecond, expression)`|  
|[Minute(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(minute, expression)`|  
|[Month(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(month, expression)`|  
|[Second(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(second, expression)`|  
|[Truncate(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|SQL Server 2000 と SQL Server 2005 で、切り捨てられた`datetime`書式設定された値は、サーバー上に作成します。 SQL Server 2008 および以降のバージョンで、切り捨てられた`datetime2`または`datetimeoffset`値が、サーバー上に作成します。|  
|[Year(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(YEAR, expression)`|  
  
## <a name="aggregate-functions"></a>集計関数  
 集計関数のマッピングを次の表に示します。  
  
|正規関数|SQL Server 関数|  
|-------------------------|--------------------------|  
|[Avg(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`AVG(expression)`|  
|[BigCount(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`BIGCOUNT(expression)`|  
|[Count(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`COUNT(expression)`|  
|[Min(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`MIN(expression)`|  
|[Max(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`MAX(expression)`|  
|[StDev(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`STDEV(expression)`|  
|[StDevP(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`STDEVP(expression)`|  
|[Sum(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`SUM(expression)`|  
|[Var(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`VAR(expression)`|  
|[VarP(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`VARP(expression)`|  
  
## <a name="math-functions"></a>数学関数  
 数学関数のマッピングを次の表に示します。  
  
|正規関数|SQL Server 関数|  
|-------------------------|--------------------------|  
|[Abs(value)](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`ABS(value)`|  
|[Ceiling(value)](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`CEILING(value)`|  
|[Floor(value)](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`FLOOR(value)`|  
|[Power(value)](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`POWER(value, exponent)`|  
|[Round(value)](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`ROUND(value, digits, 0)`|  
|[Truncate](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`ROUND(value , digits, 1)`|  
  
## <a name="string-functions"></a>文字列関数  
 文字列関数のマッピングを次の表に示します。  
  
|正規関数|SQL Server 関数|  
|-------------------------|--------------------------|  
|[Contains(string, target)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`CHARINDEX(target, string)`|  
|[Concat (string1, string2)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|string1 + string2|  
|[EndsWith (string, target)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`CHARINDEX(REVERSE(target), REVERSE(string)) = 1`<br /><br /> **注**、`CHARINDEX`関数が返される`false`場合、`string`は固定長文字列型の列に格納および`target`は定数です。 この場合、末尾の埋め込み空白も含めて文字列全体が検索されます。 この問題を回避するには、データを固定長文字列の長さに合わせて切り詰めてから、文字列を `EndsWith` 関数に渡します。たとえば、`EndsWith(TRIM(string), target)` のように指定します。|  
|[IndexOf (ターゲット、string2)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`CHARINDEX(target, string2)`|  
|[左 (string1, 長さ)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`LEFT(string1, length)`|  
|[Length (string)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`LEN(string)`|  
|[LTrim(string)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`LTRIM(string)`|  
|[右 (string1, 長さ)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`RIGHT (string1, length)`|  
|[Trim(string)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`LTRIM(RTRIM(string))`|  
|[置換 (string1、string2、string3)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`REPLACE(string1, string2, string3)`|  
|[Reverse (string)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`REVERSE (string)`|  
|[RTrim(string)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`RTRIM(string)`|  
|[StartsWith (string, target)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`CHARINDEX(target, string)`|  
|[部分文字列 (文字列、開始、長さ)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`SUBSTRING(string, start, length)`|  
|[ToLower(string)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`LOWER(string)`|  
|[ToUpper(string)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`UPPER(string)`|  
  
## <a name="bitwise-functions"></a>ビット単位の関数  
 ビット単位の関数のマッピングを次の表に示します。  
  
|正規関数|SQL Server 関数|  
|-------------------------|--------------------------|  
|[BitWiseAnd (value1, value2)](../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)|value1 & value2|  
|[Bitwisenot です (値)](../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)|~value|  
|[ビット単位の Or (value1, value2)](../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)|value1 &#124;です。value2|  
|[BitWiseXor (value1, value2)](../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)|value1 ^ value2|
