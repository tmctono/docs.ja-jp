---
title: Mailaddressparc Ser クラス (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Mail.MailAddressParser
- System.Net.Mail.MailAddressParser.ParseAddress
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: ff83f6946539fa262ccde980052627f98c75601d
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051351"
---
# <a name="mailaddressparser-class"></a><span data-ttu-id="66beb-102">MailAddressParser クラス</span><span class="sxs-lookup"><span data-stu-id="66beb-102">MailAddressParser class</span></span>

<span data-ttu-id="66beb-103">RFC 2822 で説明されているように、電子メールアドレスを解析します。</span><span class="sxs-lookup"><span data-stu-id="66beb-103">Parses email addresses as described in RFC 2822.</span></span> <span data-ttu-id="66beb-104">このクラスは継承できません。</span><span class="sxs-lookup"><span data-stu-id="66beb-104">This class cannot be inherited.</span></span>

```csharp
internal static class MailAddressParser
```

> [!WARNING]
> <span data-ttu-id="66beb-105">このクラスは内部的なものであり、コードで直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="66beb-105">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="66beb-106">Microsoft では、どのような状況でも、実稼働アプリケーションでのこのクラスの使用はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="66beb-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="parseaddress-method"></a><span data-ttu-id="66beb-107">ParseAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="66beb-107">ParseAddress method</span></span>

<span data-ttu-id="66beb-108">指定した文字列から1つの電子メールアドレスを解析します。</span><span class="sxs-lookup"><span data-stu-id="66beb-108">Parses a single email address from the specified string.</span></span>

```csharp
internal static MailAddress ParseAddress(string data)
```

### <a name="parameters"></a><span data-ttu-id="66beb-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="66beb-109">Parameters</span></span>

<span data-ttu-id="66beb-110">`data` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="66beb-110">`data` <xref:System.String></span></span>

<span data-ttu-id="66beb-111">解析する電子メールアドレスを含む文字列。</span><span class="sxs-lookup"><span data-stu-id="66beb-111">The string that contains an email address to be parsed.</span></span>

### <a name="return-value"></a><span data-ttu-id="66beb-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="66beb-112">Return value</span></span>

<xref:System.Net.Mail.MailAddress>

<span data-ttu-id="66beb-113">有効な電子メールアドレス。</span><span class="sxs-lookup"><span data-stu-id="66beb-113">A valid email address.</span></span>

### <a name="exceptions"></a><span data-ttu-id="66beb-114">例外</span><span class="sxs-lookup"><span data-stu-id="66beb-114">Exceptions</span></span>

<xref:System.FormatException?displayProperty=nameWithType>

<span data-ttu-id="66beb-115">電子メールアドレスが無効です。</span><span class="sxs-lookup"><span data-stu-id="66beb-115">The email address is invalid.</span></span>

## <a name="requirements"></a><span data-ttu-id="66beb-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="66beb-116">Requirements</span></span>

<span data-ttu-id="66beb-117">**名前空間:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="66beb-117">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="66beb-118">**アセンブリ:** システム (System.dll)</span><span class="sxs-lookup"><span data-stu-id="66beb-118">**Assembly:** System (in System.dll)</span></span>
