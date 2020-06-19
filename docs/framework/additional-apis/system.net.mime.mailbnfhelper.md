---
title: MailbSystem.Net Helper クラス ()
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Mime.MailBnfHelper
- System.Net.Mime.MailBnfHelper.Ascii7bitMaxValue
- System.Net.Mime.MailBnfHelper.Atext
- System.Net.Mime.MailBnfHelper.CR
- System.Net.Mime.MailBnfHelper.Ctext
- System.Net.Mime.MailBnfHelper.Dot
- System.Net.Mime.MailBnfHelper.EndComment
- System.Net.Mime.MailBnfHelper.LF
- System.Net.Mime.MailBnfHelper.Space
- System.Net.Mime.MailBnfHelper.StartComment
- System.Net.Mime.MailBnfHelper.Tab
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 86c98726a7886285917b6be8c7631ca1e9e425e6
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990536"
---
# <a name="mailbnfhelper-class"></a><span data-ttu-id="a8927-102">Mailbnfsd ヘルパークラス</span><span class="sxs-lookup"><span data-stu-id="a8927-102">MailBnfHelper class</span></span>

<span data-ttu-id="a8927-103">インターネットメッセージ形式の文字列を解析するためのユーティリティメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a8927-103">Contains utility methods for parsing internet message-formatted strings.</span></span> <span data-ttu-id="a8927-104">このクラスは継承できません。</span><span class="sxs-lookup"><span data-stu-id="a8927-104">This class cannot be inherited.</span></span>

```csharp
internal static class MailBnfHelper
```

> [!WARNING]
> <span data-ttu-id="a8927-105">このクラスは内部的なものであり、コードで直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="a8927-105">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="a8927-106">Microsoft では、どのような状況でも、実稼働アプリケーションでのこのクラスの使用はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="a8927-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="ascii7bitmaxvalue-field"></a><span data-ttu-id="a8927-107">Ascii7bitMaxValue フィールド</span><span class="sxs-lookup"><span data-stu-id="a8927-107">Ascii7bitMaxValue field</span></span>

<span data-ttu-id="a8927-108">7ビット Ascii 値の最大値を表します。</span><span class="sxs-lookup"><span data-stu-id="a8927-108">Represents the maximum 7-bit Ascii value.</span></span>

```csharp
internal static readonly int Ascii7bitMaxValue
```

## <a name="atext-field"></a><span data-ttu-id="a8927-109">フィールドの入力</span><span class="sxs-lookup"><span data-stu-id="a8927-109">Atext field</span></span>

<span data-ttu-id="a8927-110">アトムで使用できる文字を表します。</span><span class="sxs-lookup"><span data-stu-id="a8927-110">Represents the characters allowed in atoms.</span></span>

```csharp
internal static bool[] Atext
```

## <a name="cr-field"></a><span data-ttu-id="a8927-111">CR フィールド</span><span class="sxs-lookup"><span data-stu-id="a8927-111">CR field</span></span>

<span data-ttu-id="a8927-112">キャリッジリターン文字を表します。</span><span class="sxs-lookup"><span data-stu-id="a8927-112">Represents the carriage-return character.</span></span>

```csharp
internal static readonly char CR
```

## <a name="ctext-field"></a><span data-ttu-id="a8927-113">Ctext フィールド</span><span class="sxs-lookup"><span data-stu-id="a8927-113">Ctext field</span></span>

<span data-ttu-id="a8927-114">コメント内で使用できる文字を表します。</span><span class="sxs-lookup"><span data-stu-id="a8927-114">Represents the characters allowed inside of comments.</span></span>

```csharp
internal static bool[] Ctext
```

## <a name="dot-field"></a><span data-ttu-id="a8927-115">ドットフィールド</span><span class="sxs-lookup"><span data-stu-id="a8927-115">Dot field</span></span>

<span data-ttu-id="a8927-116">フルストップ文字 () を表し `.` ます。</span><span class="sxs-lookup"><span data-stu-id="a8927-116">Represents the full-stop character (`.`).</span></span>

```csharp
internal static readonly char Dot
```

## <a name="endcomment-field"></a><span data-ttu-id="a8927-117">EndComment フィールド</span><span class="sxs-lookup"><span data-stu-id="a8927-117">EndComment field</span></span>

<span data-ttu-id="a8927-118">コメントの末尾を指定する文字を表します。</span><span class="sxs-lookup"><span data-stu-id="a8927-118">Represents the character that specifies the end of a comment.</span></span>

```csharp
internal static readonly char EndComment
```

## <a name="lf-field"></a><span data-ttu-id="a8927-119">LF フィールド</span><span class="sxs-lookup"><span data-stu-id="a8927-119">LF field</span></span>

<span data-ttu-id="a8927-120">ラインフィード文字を表します。</span><span class="sxs-lookup"><span data-stu-id="a8927-120">Represents the line-feed character.</span></span>

```csharp
internal static readonly char LF
```

## <a name="space-field"></a><span data-ttu-id="a8927-121">スペースフィールド</span><span class="sxs-lookup"><span data-stu-id="a8927-121">Space field</span></span>

<span data-ttu-id="a8927-122">空白文字を表します。</span><span class="sxs-lookup"><span data-stu-id="a8927-122">Represents the space character.</span></span>

```csharp
internal static readonly char Space
```

## <a name="startcomment-field"></a><span data-ttu-id="a8927-123">StartComment フィールド</span><span class="sxs-lookup"><span data-stu-id="a8927-123">StartComment field</span></span>

<span data-ttu-id="a8927-124">コメントの先頭を指定する文字を表します。</span><span class="sxs-lookup"><span data-stu-id="a8927-124">Represents the character that specifies the start of a comment.</span></span>

```csharp
internal static readonly char StartComment
```

## <a name="tab-field"></a><span data-ttu-id="a8927-125">タブフィールド</span><span class="sxs-lookup"><span data-stu-id="a8927-125">Tab field</span></span>

<span data-ttu-id="a8927-126">タブ文字を表します。</span><span class="sxs-lookup"><span data-stu-id="a8927-126">Represents the tab character.</span></span>

```csharp
internal static readonly char Tab
```

## <a name="requirements"></a><span data-ttu-id="a8927-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="a8927-127">Requirements</span></span>

<span data-ttu-id="a8927-128">**名前空間:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="a8927-128">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="a8927-129">**アセンブリ:** システム (System.dll)</span><span class="sxs-lookup"><span data-stu-id="a8927-129">**Assembly:** System (in System.dll)</span></span>
