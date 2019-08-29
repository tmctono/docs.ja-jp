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
ms.openlocfilehash: 98813bf6685be78d33ebd5cc5e8c07a61a811c25
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106760"
---
# <a name="how-to-restore-time-zones-from-an-embedded-resource"></a><span data-ttu-id="037ea-102">方法: 埋め込みリソースからタイム ゾーンを復元する</span><span class="sxs-lookup"><span data-stu-id="037ea-102">How to: Restore time zones from an embedded resource</span></span>

<span data-ttu-id="037ea-103">このトピックでは、リソースファイルに保存されているタイムゾーンを復元する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="037ea-103">This topic describes how to restore time zones that have been saved in a resource file.</span></span> <span data-ttu-id="037ea-104">タイムゾーンの保存に関する情報および手順に[ついては、「方法:埋め込みリソース](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)にタイムゾーンを保存します。</span><span class="sxs-lookup"><span data-stu-id="037ea-104">For information and instructions about saving time zones, see [How to: Save time zones to an embedded resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md).</span></span>

### <a name="to-deserialize-a-timezoneinfo-object-from-an-embedded-resource"></a><span data-ttu-id="037ea-105">埋め込みリソースから TimeZoneInfo オブジェクトを逆シリアル化するには</span><span class="sxs-lookup"><span data-stu-id="037ea-105">To deserialize a TimeZoneInfo object from an embedded resource</span></span>

1. <span data-ttu-id="037ea-106">取得するタイムゾーンがカスタムタイムゾーンでない場合は、 <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>メソッドを使用してインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="037ea-106">If the time zone to be retrieved is not a custom time zone, try to instantiate it by using the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method.</span></span>

2. <span data-ttu-id="037ea-107">埋め込み<xref:System.Resources.ResourceManager>リソースファイルの完全修飾名と、リソースファイルを含むアセンブリへの参照を渡すことによって、オブジェクトをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="037ea-107">Instantiate a <xref:System.Resources.ResourceManager> object by passing the fully qualified name of the embedded resource file and a reference to the assembly that contains the resource file.</span></span>

   <span data-ttu-id="037ea-108">埋め込まれたリソースファイルの完全修飾名を特定できない場合は、 [ildasm.exe (IL 逆アセンブラー)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)を使用して、アセンブリのマニフェストを確認します。</span><span class="sxs-lookup"><span data-stu-id="037ea-108">If you cannot determine the fully qualified name of the embedded resource file, use the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to examine the assembly's manifest.</span></span> <span data-ttu-id="037ea-109">リソース`.mresource`を識別するエントリ。</span><span class="sxs-lookup"><span data-stu-id="037ea-109">An `.mresource` entry identifies the resource.</span></span> <span data-ttu-id="037ea-110">この例では、リソースの完全修飾名は`SerializeTimeZoneData.SerializedTimeZones`です。</span><span class="sxs-lookup"><span data-stu-id="037ea-110">In the example, the resource's fully qualified name is `SerializeTimeZoneData.SerializedTimeZones`.</span></span>

   <span data-ttu-id="037ea-111">リソースファイルが、タイムゾーンのインスタンス化コードを含む同じアセンブリに埋め込まれている場合は、 `static` (`Shared` Visual Basic) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A>メソッドを呼び出すことによって、そのファイルへの参照を取得できます。</span><span class="sxs-lookup"><span data-stu-id="037ea-111">If the resource file is embedded in the same assembly that contains the time zone instantiation code, you can retrieve a reference to it by calling the `static` (`Shared` in Visual Basic) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> method.</span></span>

3. <span data-ttu-id="037ea-112">メソッドの<xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>呼び出しが失敗した場合、またはカスタムタイムゾーンをインスタンス化する場合は、 <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType>メソッドを呼び出して、シリアル化されたタイムゾーンを含む文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="037ea-112">If the call to the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method fails, or if a custom time zone is to be instantiated, retrieve a string that contains the serialized time zone by calling the <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> method.</span></span>

4. <span data-ttu-id="037ea-113"><xref:System.TimeZoneInfo.FromSerializedString%2A>メソッドを呼び出してタイムゾーンデータを逆シリアル化します。</span><span class="sxs-lookup"><span data-stu-id="037ea-113">Deserialize the time zone data by calling the <xref:System.TimeZoneInfo.FromSerializedString%2A> method.</span></span>

## <a name="example"></a><span data-ttu-id="037ea-114">例</span><span class="sxs-lookup"><span data-stu-id="037ea-114">Example</span></span>

<span data-ttu-id="037ea-115">次の例では<xref:System.TimeZoneInfo> 、埋め込み .net XML リソースファイルに格納されているオブジェクトを逆シリアル化します。</span><span class="sxs-lookup"><span data-stu-id="037ea-115">The following example deserializes a <xref:System.TimeZoneInfo> object stored in an embedded .NET XML resource file.</span></span>

[!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
[!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]

<span data-ttu-id="037ea-116">このコードは、アプリケーションに必要な<xref:System.TimeZoneInfo>オブジェクトが存在することを確認するための例外処理を示しています。</span><span class="sxs-lookup"><span data-stu-id="037ea-116">This code illustrates exception handling to ensure that a <xref:System.TimeZoneInfo> object required by the application is present.</span></span> <span data-ttu-id="037ea-117">まず、 <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>メソッドを使用し<xref:System.TimeZoneInfo>てレジストリからオブジェクトを取得することによって、オブジェクトのインスタンス化を試みます。</span><span class="sxs-lookup"><span data-stu-id="037ea-117">It first tries to instantiate a <xref:System.TimeZoneInfo> object by retrieving it from the registry using the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method.</span></span> <span data-ttu-id="037ea-118">タイムゾーンをインスタンス化できない場合、コードは埋め込みリソースファイルからタイムゾーンを取得します。</span><span class="sxs-lookup"><span data-stu-id="037ea-118">If the time zone cannot be instantiated, the code retrieves it from the embedded resource file.</span></span>

<span data-ttu-id="037ea-119">カスタムタイムゾーン ( <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>メソッドを使用してインスタンス化されたタイムゾーン) のデータはレジストリに格納されないため、コードはを呼び出して、 <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>南極のタイムゾーンをインスタンス化しません。</span><span class="sxs-lookup"><span data-stu-id="037ea-119">Because data for custom time zones (time zones instantiated by using the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method) are not stored in the registry, the code does not call the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> to instantiate the time zone for Palmer, Antarctica.</span></span> <span data-ttu-id="037ea-120">代わりに、埋め込みリソースファイルをすぐに検索して、 <xref:System.TimeZoneInfo.FromSerializedString%2A>メソッドを呼び出す前にタイムゾーンのデータを含む文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="037ea-120">Instead, it immediately looks to the embedded resource file to retrieve a string that contains the time zone's data before it calls the <xref:System.TimeZoneInfo.FromSerializedString%2A> method.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="037ea-121">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="037ea-121">Compiling the code</span></span>

<span data-ttu-id="037ea-122">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="037ea-122">This example requires:</span></span>

- <span data-ttu-id="037ea-123">このプロジェクトには、System. .dll と system.servicemodel への参照を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="037ea-123">That a reference to System.Windows.Forms.dll and System.Core.dll be added to the project.</span></span>

- <span data-ttu-id="037ea-124">次の名前空間がインポートされます。</span><span class="sxs-lookup"><span data-stu-id="037ea-124">That the following namespaces be imported:</span></span>

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a><span data-ttu-id="037ea-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="037ea-125">See also</span></span>

- [<span data-ttu-id="037ea-126">日付、時刻、およびタイム ゾーン</span><span class="sxs-lookup"><span data-stu-id="037ea-126">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="037ea-127">タイム ゾーンの概要</span><span class="sxs-lookup"><span data-stu-id="037ea-127">Time zone overview</span></span>](../../../docs/standard/datetime/time-zone-overview.md)
- [<span data-ttu-id="037ea-128">方法: 埋め込みリソースにタイムゾーンを保存する</span><span class="sxs-lookup"><span data-stu-id="037ea-128">How to: Save time zones to an embedded resource</span></span>](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
