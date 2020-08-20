---
ms.openlocfilehash: 7cb146d19486618a4cee9976abe2220ea4b72790
ms.sourcegitcommit: d337df55f83325918cbbd095eb573400bea49064
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2020
ms.locfileid: "88203996"
---
### <a name="binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps"></a><span data-ttu-id="acc77-101">BinaryFormatter シリアル化メソッドが古い形式になり、ASP.NET アプリでは使用不可に</span><span class="sxs-lookup"><span data-stu-id="acc77-101">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>

<span data-ttu-id="acc77-102"><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>、<xref:System.Runtime.Serialization.Formatter>、および <xref:System.Runtime.Serialization.IFormatter> の `Serialize` メソッドと `Deserialize` メソッドが古い形式になりました。</span><span class="sxs-lookup"><span data-stu-id="acc77-102">`Serialize` and `Deserialize` methods on <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, <xref:System.Runtime.Serialization.Formatter>, and <xref:System.Runtime.Serialization.IFormatter> are now obsolete.</span></span> <span data-ttu-id="acc77-103">また、ASP.NET アプリでは、<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> のシリアル化が既定で禁止されます。</span><span class="sxs-lookup"><span data-stu-id="acc77-103">Additionally, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> serialization is prohibited by default for ASP.NET apps.</span></span>

#### <a name="change-description"></a><span data-ttu-id="acc77-104">変更の説明</span><span class="sxs-lookup"><span data-stu-id="acc77-104">Change description</span></span>

<span data-ttu-id="acc77-105"><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> の[セキュリティ脆弱性](../../../../docs/standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities)により、次のメソッドは古い形式になりました。</span><span class="sxs-lookup"><span data-stu-id="acc77-105">Due to [security vulnerabilities](../../../../docs/standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities) in <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, the following methods are now obsolete.</span></span> <span data-ttu-id="acc77-106">また、ASP.NET Core 5.0 以降のアプリでは、Web アプリによって <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 機能が再有効化されていない限り、<xref:System.NotSupportedException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="acc77-106">Additionally, in ASP.NET Core 5.0 and later apps, they will throw a <xref:System.NotSupportedException>, unless the web app has re-enabled <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> functionality.</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>

<span data-ttu-id="acc77-107">.NET エコシステム内における <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> の使用を段階的に縮小するための取り組みの一環として、これらのメソッドが古い形式としてマークされています。</span><span class="sxs-lookup"><span data-stu-id="acc77-107">These methods are marked obsolete as part of an effort to wind down usage of <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> within the .NET ecosystem.</span></span>

<span data-ttu-id="acc77-108">次のシリアル化メソッドも古い形式になりましたが、動作変更はありません。</span><span class="sxs-lookup"><span data-stu-id="acc77-108">The following serialization methods are also now obsolete, but have no behavioral changes:</span></span>

- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>

#### <a name="version-introduced"></a><span data-ttu-id="acc77-109">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="acc77-109">Version introduced</span></span>

<span data-ttu-id="acc77-110">5.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="acc77-110">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="acc77-111">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="acc77-111">Recommended action</span></span>

- <span data-ttu-id="acc77-112">コードでの <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> の使用を停止してください。</span><span class="sxs-lookup"><span data-stu-id="acc77-112">Stop using <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> in your code.</span></span> <span data-ttu-id="acc77-113">代わりに、<xref:System.Text.Json.JsonSerializer> または <xref:System.Xml.Serialization.XmlSerializer> の使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="acc77-113">Instead, consider using <xref:System.Text.Json.JsonSerializer> or <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="acc77-114">詳しくは、「[BinaryFormatter セキュリティ ガイド](../../../../docs/standard/serialization/binaryformatter-security-guide.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="acc77-114">For more information, see [BinaryFormatter security guide](../../../../docs/standard/serialization/binaryformatter-security-guide.md).</span></span>

- <span data-ttu-id="acc77-115"><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> のコンパイル時の警告 (`SYSLIB0011`) を一時的に抑制することができます。</span><span class="sxs-lookup"><span data-stu-id="acc77-115">You can temporarily suppress the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> compile-time warning, which is `SYSLIB0011`.</span></span> <span data-ttu-id="acc77-116">このオプションを選択する前に、リスクについてコードを十分に評価することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="acc77-116">We recommend that you thoroughly assess your code for risks before choosing this option.</span></span> <span data-ttu-id="acc77-117">警告を抑制する最も簡単な方法は、個々の呼び出しサイトを `#pragma` ディレクティブで囲むことです。</span><span class="sxs-lookup"><span data-stu-id="acc77-117">The easiest way to suppress the warnings is to surround the individual call site with `#pragma` directives.</span></span>

  ```csharp
  // Now read the purchase order back from disk
  using (var readStream = new FileStream("myfile.bin", FileMode.Open))
  {
      var formatter = new BinaryFormatter();
  #pragma warning disable SYSLIB0011
      return (PurchaseOrder)formatter.Deserialize(readStream);
  #pragma warning restore SYSLIB0011
  }
  ```

  <span data-ttu-id="acc77-118">また、プロジェクト ファイルで警告を抑制することもできます。</span><span class="sxs-lookup"><span data-stu-id="acc77-118">You can also suppress the warning in the project file.</span></span>

  ```xml
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Disable "BinaryFormatter is obsolete" warnings for entire project -->
    <NoWarn>$(NoWarn);SYSLIB0011</NoWarn>
  </PropertyGroup>
  ```

  <span data-ttu-id="acc77-119">プロジェクト ファイルで警告を抑制すると、プロジェクト内のすべてのコード ファイルに対して警告が抑制されます。</span><span class="sxs-lookup"><span data-stu-id="acc77-119">If you suppress the warning in the project file, the warning is suppressed for all code files in the project.</span></span> <span data-ttu-id="acc77-120">SYSLIB0011 を抑制しても、他の古い API の使用によって発生した警告は抑制されません。</span><span class="sxs-lookup"><span data-stu-id="acc77-120">Suppressing SYSLIB0011 does not suppress warnings caused by using other obsolete APIs.</span></span>

- <span data-ttu-id="acc77-121">ASP.NET アプリで引き続き <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> を使用する場合は、プロジェクト ファイルで再有効化することができます。</span><span class="sxs-lookup"><span data-stu-id="acc77-121">To continue using <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> in ASP.NET apps, you can re-enable it in the project file.</span></span> <span data-ttu-id="acc77-122">ただし、そうしないことを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="acc77-122">However, it's strongly recommended not to do this.</span></span> <span data-ttu-id="acc77-123">詳しくは、「[BinaryFormatter セキュリティ ガイド](../../../../docs/standard/serialization/binaryformatter-security-guide.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="acc77-123">For more information, see [BinaryFormatter security guide](../../../../docs/standard/serialization/binaryformatter-security-guide.md).</span></span>

  ```xml
  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Warning: Setting the following switch is *NOT* recommended in web apps. -->
    <EnableUnsafeBinaryFormatterSerialization>true</EnableUnsafeBinaryFormatterSerialization>
  </PropertyGroup>
  ```

<span data-ttu-id="acc77-124">推奨される操作の詳細については、「[BinaryFormatter の廃止と無効化に関するエラーの解決](https://aka.ms/binaryformatter)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="acc77-124">For more information about recommended actions, see [Resolving BinaryFormatter obsoletion and disablement errors](https://aka.ms/binaryformatter).</span></span>

#### <a name="category"></a><span data-ttu-id="acc77-125">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="acc77-125">Category</span></span>

- <span data-ttu-id="acc77-126">Core .NET ライブラリ</span><span class="sxs-lookup"><span data-stu-id="acc77-126">Core .NET libraries</span></span>
- <span data-ttu-id="acc77-127">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="acc77-127">ASP.NET</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="acc77-128">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="acc77-128">Affected APIs</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize`
- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize`
- `M:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)`
- `M:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)`
- `M:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)`
- `M:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)`

-->
