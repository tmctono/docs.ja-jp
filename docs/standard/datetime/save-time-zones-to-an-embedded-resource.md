---
title: '方法: 埋め込みリソースにタイムゾーンを保存する'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], saving
- time zone objects [.NET Framework], serializing
- time zone objects [.NET Framework], saving
ms.assetid: 3c96d83a-a057-4496-abb0-8f4b12712558
ms.openlocfilehash: aaee4e82d09e8b604d06dadb5a5eefe8d2e1f307
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123768"
---
# <a name="how-to-save-time-zones-to-an-embedded-resource"></a><span data-ttu-id="b5cb1-102">方法: 埋め込みリソースにタイムゾーンを保存する</span><span class="sxs-lookup"><span data-stu-id="b5cb1-102">How to: Save time zones to an embedded resource</span></span>

<span data-ttu-id="b5cb1-103">タイムゾーンに対応するアプリケーションでは、多くの場合、特定のタイムゾーンが存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5cb1-103">A time zone-aware application often requires the presence of a particular time zone.</span></span> <span data-ttu-id="b5cb1-104">ただし、個々の <xref:System.TimeZoneInfo> オブジェクトの可用性は、ローカルシステムのレジストリに格納されている情報に依存しているため、通常に使用可能なタイムゾーンも存在しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b5cb1-104">However, because the availability of individual <xref:System.TimeZoneInfo> objects depends on information stored in the local system's registry, even customarily available time zones may be absent.</span></span> <span data-ttu-id="b5cb1-105">また、<xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> メソッドを使用してインスタンス化されたカスタムタイムゾーンに関する情報は、レジストリ内の他のタイムゾーン情報と共に格納されません。</span><span class="sxs-lookup"><span data-stu-id="b5cb1-105">In addition, information about custom time zones instantiated by using the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method is not stored with other time zone information in the registry.</span></span> <span data-ttu-id="b5cb1-106">これらのタイムゾーンが必要なときに確実に使用できるようにするには、それらをシリアル化して保存し、後でそれらを逆シリアル化して復元します。</span><span class="sxs-lookup"><span data-stu-id="b5cb1-106">To ensure that these time zones are available when they are needed, you can save them by serializing them, and later restore them by deserializing them.</span></span>

<span data-ttu-id="b5cb1-107">通常、<xref:System.TimeZoneInfo> オブジェクトのシリアル化は、タイムゾーン対応アプリケーションとは別に行われます。</span><span class="sxs-lookup"><span data-stu-id="b5cb1-107">Typically, serializing a <xref:System.TimeZoneInfo> object occurs apart from the time zone-aware application.</span></span> <span data-ttu-id="b5cb1-108">シリアル化された <xref:System.TimeZoneInfo> オブジェクトの保持に使用されるデータストアによっては、タイムゾーンデータがセットアップまたはインストールルーチンの一部としてシリアル化されることがあります (たとえば、データがレジストリのアプリケーションキーに格納されている場合)。または、の前に実行するユーティリティルーチンの一部として、最終的なアプリケーションがコンパイルされます (たとえば、シリアル化されたデータが .NET XML リソース (.resx) ファイルに格納されている場合)。</span><span class="sxs-lookup"><span data-stu-id="b5cb1-108">Depending on the data store used to hold serialized <xref:System.TimeZoneInfo> objects, time zone data may be serialized as part of a setup or installation routine (for example, when the data is stored in an application key of the registry), or as part of a utility routine that runs before the final application is compiled (for example, when the serialized data is stored in a .NET XML resource (.resx) file).</span></span>

<span data-ttu-id="b5cb1-109">アプリケーションと共にコンパイルされるリソースファイルに加えて、他のいくつかのデータストアをタイムゾーン情報に使用できます。</span><span class="sxs-lookup"><span data-stu-id="b5cb1-109">In addition to a resource file that is compiled with the application, several other data stores can be used for time zone information.</span></span> <span data-ttu-id="b5cb1-110">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b5cb1-110">These include the following:</span></span>

- <span data-ttu-id="b5cb1-111">レジストリ。</span><span class="sxs-lookup"><span data-stu-id="b5cb1-111">The registry.</span></span> <span data-ttu-id="b5cb1-112">アプリケーションでは、HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Time Zones のサブキーを使用するのではなく、独自のアプリケーションキーのサブキーを使用して、カスタムタイムゾーンデータを格納する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b5cb1-112">Note that an application should use the subkeys of its own application key to store custom time zone data rather than using the subkeys of HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Time Zones.</span></span>

- <span data-ttu-id="b5cb1-113">構成ファイル。</span><span class="sxs-lookup"><span data-stu-id="b5cb1-113">Configuration files.</span></span>

- <span data-ttu-id="b5cb1-114">その他のシステムファイル。</span><span class="sxs-lookup"><span data-stu-id="b5cb1-114">Other system files.</span></span>

### <a name="to-save-a-time-zone-by-serializing-it-to-a-resx-file"></a><span data-ttu-id="b5cb1-115">.Resx ファイルにシリアル化してタイムゾーンを保存するには</span><span class="sxs-lookup"><span data-stu-id="b5cb1-115">To save a time zone by serializing it to a .resx file</span></span>

1. <span data-ttu-id="b5cb1-116">既存のタイムゾーンを取得するか、新しいタイムゾーンを作成します。</span><span class="sxs-lookup"><span data-stu-id="b5cb1-116">Retrieve an existing time zone or create a new time zone.</span></span>

   <span data-ttu-id="b5cb1-117">既存のタイムゾーンを取得する方法については、「[方法: 定義済みの UTC オブジェクトおよびローカルタイムゾーンオブジェクトにアクセス](../../../docs/standard/datetime/access-utc-and-local.md)する」および「[方法: TimeZoneInfo オブジェクトをインスタンス化](../../../docs/standard/datetime/instantiate-time-zone-info.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5cb1-117">To retrieve an existing time zone, see [How to: Access the predefined UTC and local time zone objects](../../../docs/standard/datetime/access-utc-and-local.md) and [How to: Instantiate a TimeZoneInfo object](../../../docs/standard/datetime/instantiate-time-zone-info.md).</span></span>

   <span data-ttu-id="b5cb1-118">新しいタイムゾーンを作成するには、<xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> メソッドのいずれかのオーバーロードを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b5cb1-118">To create a new time zone, call one of the overloads of the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method.</span></span> <span data-ttu-id="b5cb1-119">詳細については、「[方法: 調整規則のないタイムゾーンを作成](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)する」および「[方法: 調整規則を使用してタイムゾーンを作成する](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5cb1-119">For more information, see [How to: Create time zones without adjustment rules](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) and [How to: Create time zones with adjustment rules](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).</span></span>

2. <span data-ttu-id="b5cb1-120"><xref:System.TimeZoneInfo.ToSerializedString%2A> メソッドを呼び出して、タイムゾーンのデータを含む文字列を作成します。</span><span class="sxs-lookup"><span data-stu-id="b5cb1-120">Call the <xref:System.TimeZoneInfo.ToSerializedString%2A> method to create a string that contains the time zone's data.</span></span>

3. <span data-ttu-id="b5cb1-121">名前を指定し、必要に応じて、.resx ファイルのパスを <xref:System.IO.StreamWriter> クラスコンストラクターに渡して、<xref:System.IO.StreamWriter> オブジェクトをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="b5cb1-121">Instantiate a <xref:System.IO.StreamWriter> object by providing the name and optionally the path of the .resx file to the <xref:System.IO.StreamWriter> class constructor.</span></span>

4. <span data-ttu-id="b5cb1-122"><xref:System.IO.StreamWriter> オブジェクトを <xref:System.Resources.ResXResourceWriter> クラスコンストラクターに渡すことによって、<xref:System.Resources.ResXResourceWriter> オブジェクトをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="b5cb1-122">Instantiate a <xref:System.Resources.ResXResourceWriter> object by passing the <xref:System.IO.StreamWriter> object to the <xref:System.Resources.ResXResourceWriter> class constructor.</span></span>

5. <span data-ttu-id="b5cb1-123">タイムゾーンのシリアル化された文字列を <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="b5cb1-123">Pass the time zone's serialized string to the <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> method.</span></span>

6. <span data-ttu-id="b5cb1-124"><xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b5cb1-124">Call the <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> method.</span></span>

7. <span data-ttu-id="b5cb1-125"><xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b5cb1-125">Call the <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType> method.</span></span>

8. <span data-ttu-id="b5cb1-126"><xref:System.IO.StreamWriter.Close%2A> メソッドを呼び出して、<xref:System.IO.StreamWriter> オブジェクトを閉じます。</span><span class="sxs-lookup"><span data-stu-id="b5cb1-126">Close the <xref:System.IO.StreamWriter> object by calling its <xref:System.IO.StreamWriter.Close%2A> method.</span></span>

9. <span data-ttu-id="b5cb1-127">生成された .resx ファイルをアプリケーションの Visual Studio プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="b5cb1-127">Add the generated .resx file to the application's Visual Studio project.</span></span>

10. <span data-ttu-id="b5cb1-128">Visual Studio の **[プロパティ]** ウィンドウを使用して、.resx ファイルの **[ビルドアクション]** プロパティが **[埋め込みリソース]** に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b5cb1-128">Using the **Properties** window in Visual Studio, make sure that the .resx file's **Build Action** property is set to **Embedded Resource**.</span></span>

## <a name="example"></a><span data-ttu-id="b5cb1-129">例</span><span class="sxs-lookup"><span data-stu-id="b5cb1-129">Example</span></span>

<span data-ttu-id="b5cb1-130">次の例では、中部標準時を表す <xref:System.TimeZoneInfo> オブジェクトと、SerializedTimeZones という名前の .NET XML リソースファイルへの南極 Time を表す <xref:System.TimeZoneInfo> オブジェクトをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="b5cb1-130">The following example serializes a <xref:System.TimeZoneInfo> object that represents Central Standard Time and a <xref:System.TimeZoneInfo> object that represents the Palmer Station, Antarctica time to a .NET XML resource file that is named SerializedTimeZones.resx.</span></span> <span data-ttu-id="b5cb1-131">通常、中部標準時はレジストリで定義されています。パーマーステーション、南極はカスタムタイムゾーンです。</span><span class="sxs-lookup"><span data-stu-id="b5cb1-131">Central Standard Time is typically defined in the registry; Palmer Station, Antarctica is a custom time zone.</span></span>

[!code-csharp[TimeZone2.Serialization#1](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#1)]
[!code-vb[TimeZone2.Serialization#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#1)]

<span data-ttu-id="b5cb1-132">この例では <xref:System.TimeZoneInfo> オブジェクトをシリアル化して、コンパイル時にリソースファイルで使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="b5cb1-132">This example serializes <xref:System.TimeZoneInfo> objects so that they are available in a resource file at compile time.</span></span>

<span data-ttu-id="b5cb1-133"><xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> メソッドでは、完全なヘッダー情報が .NET XML リソースファイルに追加されるため、既存のファイルにリソースを追加するために使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="b5cb1-133">Because the <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> method adds complete header information to a .NET XML resource file, it cannot be used to add resources to an existing file.</span></span> <span data-ttu-id="b5cb1-134">この例では、SerializedTimeZones ファイルを確認し、存在する場合は、2つのシリアル化されたタイムゾーン以外のすべてのリソースを汎用 <xref:System.Collections.Generic.Dictionary%602> オブジェクトに格納することで、この処理を行います。</span><span class="sxs-lookup"><span data-stu-id="b5cb1-134">The example handles this by checking for the SerializedTimeZones.resx file and, if it exists, storing all of its resources other than the two serialized time zones to a generic <xref:System.Collections.Generic.Dictionary%602> object.</span></span> <span data-ttu-id="b5cb1-135">その後、既存のファイルが削除され、既存のリソースが新しい SerializedTimeZones ファイルに追加されます。</span><span class="sxs-lookup"><span data-stu-id="b5cb1-135">The existing file is then deleted and the existing resources are added to a new SerializedTimeZones.resx file.</span></span> <span data-ttu-id="b5cb1-136">シリアル化されたタイムゾーンデータもこのファイルに追加されます。</span><span class="sxs-lookup"><span data-stu-id="b5cb1-136">The serialized time zone data is also added to this file.</span></span>

<span data-ttu-id="b5cb1-137">リソースのキー (または**名前**) フィールドには、空白を埋め込むことはできません。</span><span class="sxs-lookup"><span data-stu-id="b5cb1-137">The key (or **Name**) fields of resources should not contain embedded spaces.</span></span> <span data-ttu-id="b5cb1-138"><xref:System.String.Replace%28System.String%2CSystem.String%29> メソッドは、リソースファイルに割り当てられる前に、タイムゾーン識別子内のすべての埋め込みスペースを削除するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="b5cb1-138">The <xref:System.String.Replace%28System.String%2CSystem.String%29> method is called to remove all embedded spaces in the time zone identifiers before they are assigned to the resource file.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="b5cb1-139">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="b5cb1-139">Compiling the code</span></span>

<span data-ttu-id="b5cb1-140">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b5cb1-140">This example requires:</span></span>

- <span data-ttu-id="b5cb1-141">このプロジェクトには、System. .dll と system.servicemodel への参照を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5cb1-141">That a reference to System.Windows.Forms.dll and System.Core.dll be added to the project.</span></span>

- <span data-ttu-id="b5cb1-142">次の名前空間がインポートされます。</span><span class="sxs-lookup"><span data-stu-id="b5cb1-142">That the following namespaces be imported:</span></span>

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a><span data-ttu-id="b5cb1-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="b5cb1-143">See also</span></span>

- [<span data-ttu-id="b5cb1-144">日付、時刻およびタイム ゾーン</span><span class="sxs-lookup"><span data-stu-id="b5cb1-144">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="b5cb1-145">タイム ゾーンの概要</span><span class="sxs-lookup"><span data-stu-id="b5cb1-145">Time zone overview</span></span>](../../../docs/standard/datetime/time-zone-overview.md)
- [<span data-ttu-id="b5cb1-146">方法: 埋め込みリソースからタイム ゾーンを復元する</span><span class="sxs-lookup"><span data-stu-id="b5cb1-146">How to: Restore time zones from an embedded resource</span></span>](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)
