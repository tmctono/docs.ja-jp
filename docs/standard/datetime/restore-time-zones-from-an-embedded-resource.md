---
title: '方法: 埋め込みリソースからタイム ゾーンを復元する'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], deserializing
- time zones [.NET Framework], restoring
ms.assetid: 6b7b4de9-da07-47e3-8f4c-823f81798ee7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 71fc4e04c87dfa3b83eabb06361d1da94a512a5e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026537"
---
# <a name="how-to-restore-time-zones-from-an-embedded-resource"></a><span data-ttu-id="2c6a1-102">方法: 埋め込みリソースからタイム ゾーンを復元する</span><span class="sxs-lookup"><span data-stu-id="2c6a1-102">How to: Restore time zones from an embedded resource</span></span>

<span data-ttu-id="2c6a1-103">このトピックでは、リソース ファイルに保存されているタイム ゾーンを復元する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2c6a1-103">This topic describes how to restore time zones that have been saved in a resource file.</span></span> <span data-ttu-id="2c6a1-104">情報およびタイム ゾーンを保存する方法の手順では、次を参照してください。[方法。埋め込みリソースにタイム ゾーンを保存](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)します。</span><span class="sxs-lookup"><span data-stu-id="2c6a1-104">For information and instructions about saving time zones, see [How to: Save time zones to an embedded resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md).</span></span>

### <a name="to-deserialize-a-timezoneinfo-object-from-an-embedded-resource"></a><span data-ttu-id="2c6a1-105">埋め込みリソースから TimeZoneInfo オブジェクトを逆シリアル化するには</span><span class="sxs-lookup"><span data-stu-id="2c6a1-105">To deserialize a TimeZoneInfo object from an embedded resource</span></span>

1. <span data-ttu-id="2c6a1-106">取得するタイム ゾーンでない場合、カスタム タイム ゾーンを使用してインスタンス化することをお試しください。、<xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="2c6a1-106">If the time zone to be retrieved is not a custom time zone, try to instantiate it by using the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method.</span></span>

2. <span data-ttu-id="2c6a1-107">インスタンスを作成、<xref:System.Resources.ResourceManager>リソース ファイルを含むアセンブリへの参照と埋め込みリソース ファイルの完全修飾名を渡すことによってオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="2c6a1-107">Instantiate a <xref:System.Resources.ResourceManager> object by passing the fully qualified name of the embedded resource file and a reference to the assembly that contains the resource file.</span></span>

   <span data-ttu-id="2c6a1-108">使用して、埋め込みリソース ファイルの完全修飾名を特定できない場合、 [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)アセンブリのマニフェストを確認します。</span><span class="sxs-lookup"><span data-stu-id="2c6a1-108">If you cannot determine the fully qualified name of the embedded resource file, use the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to examine the assembly's manifest.</span></span> <span data-ttu-id="2c6a1-109">`.mresource`エントリは、リソースを識別します。</span><span class="sxs-lookup"><span data-stu-id="2c6a1-109">An `.mresource` entry identifies the resource.</span></span> <span data-ttu-id="2c6a1-110">リソースの完全修飾名は、例では、`SerializeTimeZoneData.SerializedTimeZones`します。</span><span class="sxs-lookup"><span data-stu-id="2c6a1-110">In the example, the resource's fully qualified name is `SerializeTimeZoneData.SerializedTimeZones`.</span></span>

   <span data-ttu-id="2c6a1-111">呼び出してへの参照を取得するには、リソース ファイルは、タイム ゾーンのインスタンス化コードを含む同じアセンブリに埋め込まれている場合、 `static` (`Shared` Visual Basic で)<xref:System.Reflection.Assembly.GetExecutingAssembly%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="2c6a1-111">If the resource file is embedded in the same assembly that contains the time zone instantiation code, you can retrieve a reference to it by calling the `static` (`Shared` in Visual Basic) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> method.</span></span>

3. <span data-ttu-id="2c6a1-112">場合に呼び出し、<xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>メソッドが失敗した、またはカスタムのタイム ゾーンをインスタンス化する場合は、呼び出すことによって、シリアル化されたタイム ゾーンを格納する文字列を取得、<xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType>メソッド。</span><span class="sxs-lookup"><span data-stu-id="2c6a1-112">If the call to the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method fails, or if a custom time zone is to be instantiated, retrieve a string that contains the serialized time zone by calling the <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> method.</span></span>

4. <span data-ttu-id="2c6a1-113">呼び出すことによって、タイム ゾーン データを逆シリアル化、<xref:System.TimeZoneInfo.FromSerializedString%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="2c6a1-113">Deserialize the time zone data by calling the <xref:System.TimeZoneInfo.FromSerializedString%2A> method.</span></span>

## <a name="example"></a><span data-ttu-id="2c6a1-114">例</span><span class="sxs-lookup"><span data-stu-id="2c6a1-114">Example</span></span>

<span data-ttu-id="2c6a1-115">次の例では、逆シリアル化、 <xref:System.TimeZoneInfo> embedded .NET XML リソース ファイルに格納されているオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="2c6a1-115">The following example deserializes a <xref:System.TimeZoneInfo> object stored in an embedded .NET XML resource file.</span></span>

[!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
[!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]

<span data-ttu-id="2c6a1-116">このコードは、ことを確認する例外処理を示しています、<xref:System.TimeZoneInfo>アプリケーションで必要なオブジェクトが存在します。</span><span class="sxs-lookup"><span data-stu-id="2c6a1-116">This code illustrates exception handling to ensure that a <xref:System.TimeZoneInfo> object required by the application is present.</span></span> <span data-ttu-id="2c6a1-117">インスタンスを作成するときはまず、<xref:System.TimeZoneInfo>オブジェクトを使用して、レジストリから取得して、<xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="2c6a1-117">It first tries to instantiate a <xref:System.TimeZoneInfo> object by retrieving it from the registry using the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method.</span></span> <span data-ttu-id="2c6a1-118">タイム ゾーンをインスタンス化できない場合は、埋め込みリソース ファイルから取得します。</span><span class="sxs-lookup"><span data-stu-id="2c6a1-118">If the time zone cannot be instantiated, the code retrieves it from the embedded resource file.</span></span>

<span data-ttu-id="2c6a1-119">ため、カスタムのタイム ゾーンのデータ (を使用してインスタンスのタイム ゾーン、<xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>メソッド) が格納されていないレジストリで、コードを呼び出すことはできません、 <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> Palmer、南極大陸のタイム ゾーンをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="2c6a1-119">Because data for custom time zones (time zones instantiated by using the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method) are not stored in the registry, the code does not call the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> to instantiate the time zone for Palmer, Antarctica.</span></span> <span data-ttu-id="2c6a1-120">呼び出す前に、タイム ゾーンのデータを含む文字列を取得する埋め込みリソース ファイルをすぐに確認、代わりに、<xref:System.TimeZoneInfo.FromSerializedString%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="2c6a1-120">Instead, it immediately looks to the embedded resource file to retrieve a string that contains the time zone's data before it calls the <xref:System.TimeZoneInfo.FromSerializedString%2A> method.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="2c6a1-121">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="2c6a1-121">Compiling the code</span></span>

<span data-ttu-id="2c6a1-122">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2c6a1-122">This example requires:</span></span>

* <span data-ttu-id="2c6a1-123">System.Windows.Forms.dll、System.Core.dll への参照をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="2c6a1-123">That a reference to System.Windows.Forms.dll and System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="2c6a1-124">次の名前空間は、インポートします。</span><span class="sxs-lookup"><span data-stu-id="2c6a1-124">That the following namespaces be imported:</span></span>

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a><span data-ttu-id="2c6a1-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="2c6a1-125">See also</span></span>

- [<span data-ttu-id="2c6a1-126">日付、時刻、およびタイム ゾーン</span><span class="sxs-lookup"><span data-stu-id="2c6a1-126">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="2c6a1-127">タイム ゾーンの概要</span><span class="sxs-lookup"><span data-stu-id="2c6a1-127">Time zone overview</span></span>](../../../docs/standard/datetime/time-zone-overview.md)
- [<span data-ttu-id="2c6a1-128">方法: 埋め込みリソースにタイム ゾーンを保存します。</span><span class="sxs-lookup"><span data-stu-id="2c6a1-128">How to: Save time zones to an embedded resource</span></span>](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
