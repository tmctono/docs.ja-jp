---
title: '方法: 埋め込みリソースからタイムゾーンを復元する'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], deserializing
- time zones [.NET Framework], restoring
ms.assetid: 6b7b4de9-da07-47e3-8f4c-823f81798ee7
ms.openlocfilehash: cd2119d6d22f3f676b7167ed545aeb058123cfb5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122203"
---
# <a name="how-to-restore-time-zones-from-an-embedded-resource"></a><span data-ttu-id="960c6-102">方法: 埋め込みリソースからタイムゾーンを復元する</span><span class="sxs-lookup"><span data-stu-id="960c6-102">How to: Restore time zones from an embedded resource</span></span>

<span data-ttu-id="960c6-103">このトピックでは、リソースファイルに保存されているタイムゾーンを復元する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="960c6-103">This topic describes how to restore time zones that have been saved in a resource file.</span></span> <span data-ttu-id="960c6-104">タイムゾーンの保存に関する情報および手順については、「[方法: 埋め込みリソースにタイムゾーンを保存する](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="960c6-104">For information and instructions about saving time zones, see [How to: Save time zones to an embedded resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md).</span></span>

### <a name="to-deserialize-a-timezoneinfo-object-from-an-embedded-resource"></a><span data-ttu-id="960c6-105">埋め込みリソースから TimeZoneInfo オブジェクトを逆シリアル化するには</span><span class="sxs-lookup"><span data-stu-id="960c6-105">To deserialize a TimeZoneInfo object from an embedded resource</span></span>

1. <span data-ttu-id="960c6-106">取得するタイムゾーンがカスタムタイムゾーンでない場合は、<xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> メソッドを使用してインスタンス化してみてください。</span><span class="sxs-lookup"><span data-stu-id="960c6-106">If the time zone to be retrieved is not a custom time zone, try to instantiate it by using the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method.</span></span>

2. <span data-ttu-id="960c6-107">埋め込みリソースファイルの完全修飾名と、そのリソースファイルを含むアセンブリへの参照を渡すことによって、<xref:System.Resources.ResourceManager> オブジェクトをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="960c6-107">Instantiate a <xref:System.Resources.ResourceManager> object by passing the fully qualified name of the embedded resource file and a reference to the assembly that contains the resource file.</span></span>

   <span data-ttu-id="960c6-108">埋め込まれたリソースファイルの完全修飾名を特定できない場合は、 [ildasm.exe (IL 逆アセンブラー)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)を使用して、アセンブリのマニフェストを確認します。</span><span class="sxs-lookup"><span data-stu-id="960c6-108">If you cannot determine the fully qualified name of the embedded resource file, use the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to examine the assembly's manifest.</span></span> <span data-ttu-id="960c6-109">リソースを識別する `.mresource` エントリ。</span><span class="sxs-lookup"><span data-stu-id="960c6-109">An `.mresource` entry identifies the resource.</span></span> <span data-ttu-id="960c6-110">この例では、リソースの完全修飾名は `SerializeTimeZoneData.SerializedTimeZones`です。</span><span class="sxs-lookup"><span data-stu-id="960c6-110">In the example, the resource's fully qualified name is `SerializeTimeZoneData.SerializedTimeZones`.</span></span>

   <span data-ttu-id="960c6-111">リソースファイルがタイムゾーンのインスタンス化コードを含む同じアセンブリに埋め込まれている場合は、`static` (Visual Basic では`Shared`) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> メソッドを呼び出すことによって、そのファイルへの参照を取得できます。</span><span class="sxs-lookup"><span data-stu-id="960c6-111">If the resource file is embedded in the same assembly that contains the time zone instantiation code, you can retrieve a reference to it by calling the `static` (`Shared` in Visual Basic) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> method.</span></span>

3. <span data-ttu-id="960c6-112"><xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> メソッドの呼び出しが失敗した場合、またはカスタムタイムゾーンをインスタンス化する場合は、<xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> メソッドを呼び出して、シリアル化されたタイムゾーンを含む文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="960c6-112">If the call to the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method fails, or if a custom time zone is to be instantiated, retrieve a string that contains the serialized time zone by calling the <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> method.</span></span>

4. <span data-ttu-id="960c6-113"><xref:System.TimeZoneInfo.FromSerializedString%2A> メソッドを呼び出してタイムゾーンデータを逆シリアル化します。</span><span class="sxs-lookup"><span data-stu-id="960c6-113">Deserialize the time zone data by calling the <xref:System.TimeZoneInfo.FromSerializedString%2A> method.</span></span>

## <a name="example"></a><span data-ttu-id="960c6-114">例</span><span class="sxs-lookup"><span data-stu-id="960c6-114">Example</span></span>

<span data-ttu-id="960c6-115">次の例では、埋め込み .NET XML リソースファイルに格納されている <xref:System.TimeZoneInfo> オブジェクトを逆シリアル化します。</span><span class="sxs-lookup"><span data-stu-id="960c6-115">The following example deserializes a <xref:System.TimeZoneInfo> object stored in an embedded .NET XML resource file.</span></span>

[!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
[!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]

<span data-ttu-id="960c6-116">このコードは、アプリケーションに必要な <xref:System.TimeZoneInfo> オブジェクトが存在することを確認するための例外処理を示しています。</span><span class="sxs-lookup"><span data-stu-id="960c6-116">This code illustrates exception handling to ensure that a <xref:System.TimeZoneInfo> object required by the application is present.</span></span> <span data-ttu-id="960c6-117">まず、<xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> メソッドを使用してレジストリから取得することで、<xref:System.TimeZoneInfo> オブジェクトのインスタンス化を試みます。</span><span class="sxs-lookup"><span data-stu-id="960c6-117">It first tries to instantiate a <xref:System.TimeZoneInfo> object by retrieving it from the registry using the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method.</span></span> <span data-ttu-id="960c6-118">タイムゾーンをインスタンス化できない場合、コードは埋め込みリソースファイルからタイムゾーンを取得します。</span><span class="sxs-lookup"><span data-stu-id="960c6-118">If the time zone cannot be instantiated, the code retrieves it from the embedded resource file.</span></span>

<span data-ttu-id="960c6-119">カスタムタイムゾーン (<xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> メソッドを使用してインスタンス化されたタイムゾーン) のデータはレジストリに格納されないため、コードは、南極のタイムゾーンをインスタンス化するための <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> を呼び出しません。</span><span class="sxs-lookup"><span data-stu-id="960c6-119">Because data for custom time zones (time zones instantiated by using the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method) are not stored in the registry, the code does not call the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> to instantiate the time zone for Palmer, Antarctica.</span></span> <span data-ttu-id="960c6-120">代わりに、埋め込みリソースファイルをすぐに検索して、<xref:System.TimeZoneInfo.FromSerializedString%2A> メソッドを呼び出す前にタイムゾーンのデータを含む文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="960c6-120">Instead, it immediately looks to the embedded resource file to retrieve a string that contains the time zone's data before it calls the <xref:System.TimeZoneInfo.FromSerializedString%2A> method.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="960c6-121">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="960c6-121">Compiling the code</span></span>

<span data-ttu-id="960c6-122">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="960c6-122">This example requires:</span></span>

- <span data-ttu-id="960c6-123">このプロジェクトには、System. .dll と system.servicemodel への参照を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="960c6-123">That a reference to System.Windows.Forms.dll and System.Core.dll be added to the project.</span></span>

- <span data-ttu-id="960c6-124">次の名前空間がインポートされます。</span><span class="sxs-lookup"><span data-stu-id="960c6-124">That the following namespaces be imported:</span></span>

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a><span data-ttu-id="960c6-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="960c6-125">See also</span></span>

- [<span data-ttu-id="960c6-126">日付、時刻およびタイム ゾーン</span><span class="sxs-lookup"><span data-stu-id="960c6-126">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="960c6-127">タイム ゾーンの概要</span><span class="sxs-lookup"><span data-stu-id="960c6-127">Time zone overview</span></span>](../../../docs/standard/datetime/time-zone-overview.md)
- [<span data-ttu-id="960c6-128">方法: 埋め込みリソースにタイム ゾーンを保存する</span><span class="sxs-lookup"><span data-stu-id="960c6-128">How to: Save time zones to an embedded resource</span></span>](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
