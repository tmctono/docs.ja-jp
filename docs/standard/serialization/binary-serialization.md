---
title: バイナリ シリアル化
ms.date: 01/02/2018
helpviewer_keywords:
- binary serialization
- serialization, about serialization
- deserialization
- binary serialization, about serialization
- binary serialization, .net core serialization
- serialization, cross-framework
ms.assetid: 2b1ea3be-1152-4032-b2b3-07794054c405
author: ViktorHofer
ms.openlocfilehash: 9df9b73a1a1347b952d76b76c9058578f5e9f401
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401269"
---
# <a name="binary-serialization"></a><span data-ttu-id="b39e5-102">バイナリ シリアル化</span><span class="sxs-lookup"><span data-stu-id="b39e5-102">Binary serialization</span></span>

<span data-ttu-id="b39e5-103">シリアル化は、オブジェクトの状態をストレージ メディアに格納するプロセスとして定義することができます。</span><span class="sxs-lookup"><span data-stu-id="b39e5-103">Serialization can be defined as the process of storing the state of an object to a storage medium.</span></span> <span data-ttu-id="b39e5-104">このプロセスの実行中に、オブジェクトのパブリックおよびプライベートなフィールドとクラス (クラスを格納しているアセンブリを含む) の名前がバイト ストリームに変換され、データ ストリームに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="b39e5-104">During this process, the public and private fields of the object and the name of the class, including the assembly containing the class, are converted to a stream of bytes, which is then written to a data stream.</span></span> <span data-ttu-id="b39e5-105">続いてオブジェクトが逆シリアル化され、元のオブジェクトの完全な複製が作成されます。</span><span class="sxs-lookup"><span data-stu-id="b39e5-105">When the object is subsequently deserialized, an exact clone of the original object is created.</span></span>

<span data-ttu-id="b39e5-106">オブジェクト指向環境でシリアル化機構を実装する場合は、使いやすさと柔軟性の間での数多くのトレードオフについて考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-106">When implementing a serialization mechanism in an object-oriented environment, you have to make a number of tradeoffs between ease of use and flexibility.</span></span> <span data-ttu-id="b39e5-107">プロセスを十分に制御できる場合は、プロセスの大部分を自動化できます。</span><span class="sxs-lookup"><span data-stu-id="b39e5-107">The process can be automated to a large extent, provided you are given sufficient control over the process.</span></span> <span data-ttu-id="b39e5-108">たとえば、単純なバイナリ シリアル化では不十分な状況が発生する場合や、シリアル化が必要なクラス内のフィールドを決定するだけの明確な理由がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-108">For example, situations may arise where simple binary serialization is not sufficient, or there might be a specific reason to decide which fields in a class need to be serialized.</span></span> <span data-ttu-id="b39e5-109">以下のセクションでは、.NET に用意されている堅牢なシリアル化機構について検討し、必要に応じてプロセスをカスタマイズするためのいくつかの重要な機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="b39e5-109">The following sections examine the robust serialization mechanism provided with .NET and highlight a number of important features that allow you to customize the process to meet your needs.</span></span>

> [!NOTE]
> <span data-ttu-id="b39e5-110">オブジェクトのシリアル化と逆シリアル化を行う際に使用した .NET Framework のバージョンが異なる場合、UTF-8 または UTF-7 でエンコードされたオブジェクトの状態は保持されません。</span><span class="sxs-lookup"><span data-stu-id="b39e5-110">The state of a UTF-8 or UTF-7 encoded object is not preserved if the object is serialized and deserialized using different .NET Framework versions.</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

<span data-ttu-id="b39e5-111">バイナリ シリアル化を使用すると、オブジェクト内のプライベート メンバーを変更できるため、その状態を変更できます。</span><span class="sxs-lookup"><span data-stu-id="b39e5-111">Binary serialization allows modifying private members inside an object and therefore changing the state of it.</span></span> <span data-ttu-id="b39e5-112">このため、パブリック API サーフェスで動作する<xref:System.Text.Json?displayProperty=fullName>他のシリアル化フレームワーク (など) をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b39e5-112">Because of this, other serialization frameworks, like <xref:System.Text.Json?displayProperty=fullName>, that operate on the public API surface are recommended.</span></span>

## <a name="net-core"></a><span data-ttu-id="b39e5-113">.NET Core</span><span class="sxs-lookup"><span data-stu-id="b39e5-113">.NET Core</span></span>

<span data-ttu-id="b39e5-114">.NET Core では、型のサブセットに対してバイナリ シリアル化がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b39e5-114">.NET Core supports binary serialization for a subset of types.</span></span> <span data-ttu-id="b39e5-115">サポートされている型の一覧については、次の[「シリアル化可能な型](#serializable-types)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b39e5-115">You can see the list of supported types in the [Serializable types](#serializable-types) section that follows.</span></span> <span data-ttu-id="b39e5-116">ここに示されている型は、.NET Framework 4.5.1 以降のバージョン間、および .NET Core 2.0 以降のバージョン間でシリアル化できることが保証されています。</span><span class="sxs-lookup"><span data-stu-id="b39e5-116">The listed types are guaranteed to be serializable between .NET Framework 4.5.1 and later versions and between .NET Core 2.0 and later versions.</span></span> <span data-ttu-id="b39e5-117">Mono などの他の .NET 実装は公式にはサポートされていませんが、動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-117">Other .NET implementations, such as Mono, aren't officially supported but should also work.</span></span>

### <a name="serializable-types"></a><span data-ttu-id="b39e5-118">シリアル化可能な型</span><span class="sxs-lookup"><span data-stu-id="b39e5-118">Serializable types</span></span>

> [!div class="mx-tdCol2BreakAll"]
> | <span data-ttu-id="b39e5-119">Type</span><span class="sxs-lookup"><span data-stu-id="b39e5-119">Type</span></span> | <span data-ttu-id="b39e5-120">Notes</span><span class="sxs-lookup"><span data-stu-id="b39e5-120">Notes</span></span> |
> | - | - |
> | <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-121">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-121">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderInternalCompilerException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-122">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-122">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AccessViolationException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-123">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-123">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AggregateException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-124">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-124">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AppDomainUnloadedException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-125">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-125">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ApplicationException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-126">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-126">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-127">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-127">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentNullException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-128">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-128">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentOutOfRangeException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-129">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-129">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArithmeticException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-130">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-130">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Array?displayProperty=nameWithType> | |
> | <xref:System.ArraySegment%601?displayProperty=nameWithType> | |
> | <xref:System.ArrayTypeMismatchException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-131">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-131">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Attribute?displayProperty=nameWithType> | |
> | <xref:System.BadImageFormatException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-132">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-132">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Boolean?displayProperty=nameWithType> | |
> | <xref:System.Byte?displayProperty=nameWithType> | |
> | <xref:System.CannotUnloadAppDomainException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-133">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-133">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Char?displayProperty=nameWithType> | |
> | <xref:System.Collections.ArrayList?displayProperty=nameWithType> | |
> | <xref:System.Collections.BitArray?displayProperty=nameWithType> | |
> | <xref:System.Collections.Comparer?displayProperty=nameWithType> | |
> | <xref:System.Collections.DictionaryEntry?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Comparer%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.EqualityComparer%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.HashSet%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-134">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-134">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Collections.Generic.KeyValuePair%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.LinkedList%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.SortedList%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.SortedSet%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Stack%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Hashtable?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.Collection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.KeyedCollection%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ReadOnlyCollection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ReadOnlyDictionary%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Queue?displayProperty=nameWithType> | |
> | <xref:System.Collections.SortedList?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.HybridDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.ListDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.OrderedDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.StringCollection?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.StringDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Stack?displayProperty=nameWithType> | |
> | `System.Collections.Generic.NonRandomizedStringEqualityComparer` | <span data-ttu-id="b39e5-135">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-135">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.BindingList%601?displayProperty=nameWithType> | |
> | <xref:System.ComponentModel.DataAnnotations.ValidationException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-136">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-136">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.Design.CheckoutException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-137">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-137">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.InvalidAsynchronousStateException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-138">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-138">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.InvalidEnumArgumentException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-139">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-139">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.LicenseException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-140">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-140">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="b39e5-141">.NET Framework から .NET Core へのシリアル化はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b39e5-141">Serialization from .NET Framework to .NET Core is not supported.</span></span> |
> | <xref:System.ComponentModel.WarningException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-142">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-142">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.Win32Exception?displayProperty=nameWithType> | <span data-ttu-id="b39e5-143">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-143">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.ConfigurationErrorsException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-144">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-144">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.ConfigurationException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-145">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-145">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.Provider.ProviderException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-146">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-146">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyIsReadOnlyException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-147">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-147">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-148">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-148">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyWrongTypeException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-149">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-149">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ContextMarshalException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-150">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-150">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DBNull?displayProperty=nameWithType> | <span data-ttu-id="b39e5-151">NET Core 2.0.2 以降のバージョンから開始します。</span><span class="sxs-lookup"><span data-stu-id="b39e5-151">Starting in .NET Core 2.0.2 and later versions.</span></span> |
> | <xref:System.Data.Common.DbException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-152">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-152">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.ConstraintException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-153">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-153">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DBConcurrencyException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-154">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-154">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DataException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-155">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-155">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DataSet?displayProperty=nameWithType> | |
> | <xref:System.Data.DataTable?displayProperty=nameWithType> | <span data-ttu-id="b39e5-156">に`RemotingFormat``SerializationFormat.Binary`設定した場合、.NET Core 2.1 以降のバージョンとのみ交換できます。</span><span class="sxs-lookup"><span data-stu-id="b39e5-156">If you set `RemotingFormat` to `SerializationFormat.Binary`, it can only be exchanged with .NET Core 2.1 and later versions.</span></span> |
> | <xref:System.Data.DeletedRowInaccessibleException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-157">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-157">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DuplicateNameException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-158">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-158">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.EvaluateException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-159">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-159">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InRowChangingEventException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-160">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-160">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InvalidConstraintException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-161">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-161">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InvalidExpressionException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-162">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-162">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.MissingPrimaryKeyException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-163">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-163">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.NoNullAllowedException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-164">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-164">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.Odbc.OdbcException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-165">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-165">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.OperationAbortedException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-166">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-166">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.PropertyCollection?displayProperty=nameWithType> | |
> | <xref:System.Data.ReadOnlyException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-167">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-167">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.RowNotInTableException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-168">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-168">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlClient.SqlException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-169">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-169">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="b39e5-170">.NET Framework から .NET Core へのシリアル化はサポートされていません</span><span class="sxs-lookup"><span data-stu-id="b39e5-170">Serialization from .NET Framework to .NET Core is not supported</span></span> |
> | <xref:System.Data.SqlTypes.SqlAlreadyFilledException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-171">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-171">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlBoolean?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlByte?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlDateTime?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlDouble?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlGuid?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt16?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt32?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt64?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlNotFilledException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-172">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-172">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlNullValueException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-173">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-173">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlString?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlTruncateException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-174">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-174">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlTypeException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-175">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-175">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.StrongTypingException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-176">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-176">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SyntaxErrorException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-177">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-177">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.VersionNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-178">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-178">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DataMisalignedException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-179">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-179">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DateTime?displayProperty=nameWithType> | |
> | <xref:System.DateTimeOffset?displayProperty=nameWithType> | |
> | <xref:System.Decimal?displayProperty=nameWithType> | |
> | `System.Diagnostics.Contracts.ContractException` | <span data-ttu-id="b39e5-180">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-180">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Diagnostics.Tracing.EventSourceException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-181">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-181">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.DirectoryNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-182">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-182">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.MultipleMatchesException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-183">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-183">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.NoMatchingPrincipalException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-184">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-184">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PasswordException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-185">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-185">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-186">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-186">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalExistsException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-187">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-187">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalOperationException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-188">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-188">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalServerDownException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-189">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-189">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectExistsException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-190">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-190">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-191">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-191">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryOperationException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-192">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-192">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryServerDownException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-193">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-193">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ForestTrustCollisionException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-194">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-194">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.SyncFromAllServersOperationException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-195">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-195">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.DirectoryServicesCOMException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-196">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-196">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.BerConversionException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-197">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-197">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.DirectoryException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-198">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-198">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.DirectoryOperationException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-199">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-199">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.LdapException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-200">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-200">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.TlsOperationException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-201">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-201">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DivideByZeroException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-202">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-202">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DllNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-203">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-203">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Double?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Color?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Point?displayProperty=nameWithType> | |
> | <xref:System.Drawing.PointF?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Rectangle?displayProperty=nameWithType> | |
> | <xref:System.Drawing.RectangleF?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Size?displayProperty=nameWithType> | |
> | <xref:System.Drawing.SizeF?displayProperty=nameWithType> | |
> | <xref:System.DuplicateWaitObjectException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-204">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-204">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.EntryPointNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-205">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-205">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Enum?displayProperty=nameWithType> | |
> | <xref:System.EventArgs?displayProperty=nameWithType> | <span data-ttu-id="b39e5-206">NET コア 2.0.6 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-206">Starting in .NET Core 2.0.6.</span></span> |
> | <xref:System.Exception?displayProperty=nameWithType> | |
> | <xref:System.ExecutionEngineException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-207">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-207">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.FieldAccessException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-208">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-208">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.FormatException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-209">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-209">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> | |
> | <xref:System.Globalization.CultureNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-210">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-210">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Globalization.SortVersion?displayProperty=nameWithType> | |
> | <xref:System.Guid?displayProperty=nameWithType> | |
> | `System.IO.Compression.ZLibException` | <span data-ttu-id="b39e5-211">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-211">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.DriveNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-212">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-212">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.EndOfStreamException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-213">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-213">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileFormatException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-214">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-214">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileLoadException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-215">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-215">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-216">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-216">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.IOException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-217">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-217">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.InternalBufferOverflowException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-218">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-218">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.InvalidDataException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-219">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-219">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.IsolatedStorage.IsolatedStorageException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-220">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-220">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.PathTooLongException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-221">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-221">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IndexOutOfRangeException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-222">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-222">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InsufficientExecutionStackException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-223">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-223">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InsufficientMemoryException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-224">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-224">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Int16?displayProperty=nameWithType> | |
> | <xref:System.Int32?displayProperty=nameWithType> | |
> | <xref:System.Int64?displayProperty=nameWithType> | |
> | <xref:System.IntPtr?displayProperty=nameWithType> | |
> | <xref:System.InvalidCastException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-225">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-225">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidOperationException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-226">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-226">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidProgramException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-227">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-227">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidTimeZoneException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-228">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-228">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MemberAccessException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-229">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-229">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MethodAccessException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-230">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-230">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingFieldException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-231">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-231">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingMemberException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-232">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-232">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingMethodException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-233">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-233">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MulticastNotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-234">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-234">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Cookie?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieCollection?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieContainer?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-235">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-235">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.HttpListenerException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-236">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-236">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-237">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-237">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpFailedRecipientException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-238">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-238">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpFailedRecipientsException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-239">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-239">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.NetworkInformation.NetworkInformationException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-240">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-240">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.NetworkInformation.PingException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-241">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-241">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.ProtocolViolationException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-242">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-242">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Sockets.SocketException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-243">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-243">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.WebException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-244">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-244">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.WebSockets.WebSocketException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-245">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-245">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotFiniteNumberException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-246">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-246">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotImplementedException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-247">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-247">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-248">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-248">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NullReferenceException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-249">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-249">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Nullable%601?displayProperty=nameWithType> | |
> | <xref:System.Numerics.BigInteger?displayProperty=nameWithType> | |
> | <xref:System.Numerics.Complex?displayProperty=nameWithType> | |
> | <xref:System.Object?displayProperty=nameWithType> | |
> | <xref:System.ObjectDisposedException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-250">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-250">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OperationCanceledException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-251">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-251">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OutOfMemoryException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-252">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-252">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OverflowException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-253">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-253">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.PlatformNotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-254">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-254">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.RankException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-255">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-255">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.AmbiguousMatchException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-256">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-256">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.CustomAttributeFormatException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-257">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-257">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.InvalidFilterCriteriaException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-258">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-258">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.ReflectionTypeLoadException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-259">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-259">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="b39e5-260">.NET Framework から .NET Core へのシリアル化はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b39e5-260">Serialization from .NET Framework to .NET Core is not supported.</span></span> |
> | <xref:System.Reflection.TargetException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-261">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-261">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.TargetInvocationException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-262">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-262">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.TargetParameterCountException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-263">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-263">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Resources.MissingManifestResourceException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-264">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-264">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Resources.MissingSatelliteAssemblyException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-265">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-265">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.CompilerServices.RuntimeWrappedException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-266">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-266">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.COMException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-267">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-267">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.ExternalException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-268">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-268">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.InvalidComObjectException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-269">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-269">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.InvalidOleVariantTypeException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-270">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-270">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.MarshalDirectiveException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-271">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-271">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SEHException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-272">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-272">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-273">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-273">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-274">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-274">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.Serialization.InvalidDataContractException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-275">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-275">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.Serialization.SerializationException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-276">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-276">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.SByte?displayProperty=nameWithType> | |
> | <xref:System.Security.AccessControl.PrivilegeNotHeldException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-277">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-277">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Authentication.AuthenticationException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-278">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-278">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Authentication.InvalidCredentialException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-279">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-279">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Cryptography.CryptographicException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-280">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-280">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Cryptography.CryptographicUnexpectedOperationException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-281">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-281">Starting in .NET Core 2.0.4.</span></span> |
> | `System.Security.Cryptography.Xml.CryptoSignedXmlRecursionException` | <span data-ttu-id="b39e5-282">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-282">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.HostProtectionException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-283">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-283">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Policy.PolicyException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-284">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-284">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Principal.IdentityNotMappedException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-285">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-285">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.SecurityException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-286">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-286">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="b39e5-287">限定されたシリアル化データ。</span><span class="sxs-lookup"><span data-stu-id="b39e5-287">Limited serialization data.</span></span> |
> | <xref:System.Security.VerificationException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-288">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-288">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.XmlSyntaxException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-289">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-289">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ServiceProcess.TimeoutException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-290">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-290">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Single?displayProperty=nameWithType> | |
> | <xref:System.StackOverflowException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-291">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-291">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.String?displayProperty=nameWithType> | |
> | <xref:System.StringComparer?displayProperty=nameWithType> | |
> | <xref:System.SystemException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-292">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-292">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.DecoderFallbackException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-293">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-293">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.EncoderFallbackException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-294">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-294">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.RegularExpressions.RegexMatchTimeoutException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-295">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-295">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.StringBuilder?displayProperty=nameWithType> | |
> | <xref:System.Threading.AbandonedMutexException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-296">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-296">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.BarrierPostPhaseException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-297">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-297">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.LockRecursionException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-298">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-298">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.SemaphoreFullException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-299">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-299">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.SynchronizationLockException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-300">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-300">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.Tasks.TaskCanceledException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-301">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-301">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.Tasks.TaskSchedulerException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-302">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-302">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadAbortException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-303">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-303">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadInterruptedException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-304">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-304">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadStartException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-305">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-305">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadStateException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-306">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-306">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.WaitHandleCannotBeOpenedException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-307">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-307">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TimeSpan?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneInfo.AdjustmentRule?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneInfo?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-308">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-308">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TimeoutException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-309">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-309">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionAbortedException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-310">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-310">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-311">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-311">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionInDoubtException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-312">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-312">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionManagerCommunicationException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-313">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-313">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionPromotionException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-314">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-314">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Tuple?displayProperty=nameWithType> | |
> | <xref:System.TypeAccessException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-315">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-315">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeInitializationException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-316">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-316">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeLoadException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-317">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-317">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeUnloadedException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-318">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-318">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.UInt16?displayProperty=nameWithType> | |
> | <xref:System.UInt32?displayProperty=nameWithType> | |
> | <xref:System.UInt64?displayProperty=nameWithType> | |
> | <xref:System.UIntPtr?displayProperty=nameWithType> | |
> | <xref:System.UnauthorizedAccessException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-319">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-319">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Uri?displayProperty=nameWithType> | |
> | <xref:System.UriFormatException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-320">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-320">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ValueTuple?displayProperty=nameWithType> | <span data-ttu-id="b39e5-321">.NET Framework 4.7 以前のバージョンではシリアル化できません。</span><span class="sxs-lookup"><span data-stu-id="b39e5-321">Not serializable in .NET Framework 4.7 and earlier versions.</span></span> |
> | <xref:System.ValueType?displayProperty=nameWithType> | |
> | <xref:System.Version?displayProperty=nameWithType> | |
> | <xref:System.WeakReference%601?displayProperty=nameWithType> | |
> | <xref:System.WeakReference?displayProperty=nameWithType> | |
> | <xref:System.Xml.Schema.XmlSchemaException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-322">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-322">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Schema.XmlSchemaInferenceException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-323">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-323">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Schema.XmlSchemaValidationException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-324">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-324">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.XPath.XPathException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-325">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-325">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.XmlException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-326">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-326">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Xsl.XsltCompileException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-327">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-327">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Xsl.XsltException?displayProperty=nameWithType> | <span data-ttu-id="b39e5-328">NET コア 2.0.4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="b39e5-328">Starting in .NET Core 2.0.4.</span></span> |

## <a name="see-also"></a><span data-ttu-id="b39e5-329">関連項目</span><span class="sxs-lookup"><span data-stu-id="b39e5-329">See also</span></span>

- <xref:System.Runtime.Serialization>\
<span data-ttu-id="b39e5-330">オブジェクトのシリアル化と逆シリアル化に使用できるクラスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b39e5-330">Contains classes that can be used for serializing and deserializing objects.</span></span>

- <span data-ttu-id="b39e5-331">[XML および SOAP シリアル化](../../../docs/standard/serialization/xml-and-soap-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="b39e5-331">[XML and SOAP Serialization](../../../docs/standard/serialization/xml-and-soap-serialization.md)</span></span>\
<span data-ttu-id="b39e5-332">共通言語ランタイムに付属している XML シリアル化機構について説明します。</span><span class="sxs-lookup"><span data-stu-id="b39e5-332">Describes the XML serialization mechanism that is included with the common language runtime.</span></span>

- <span data-ttu-id="b39e5-333">[セキュリティとシリアル化](../../../docs/framework/misc/security-and-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="b39e5-333">[Security and Serialization](../../../docs/framework/misc/security-and-serialization.md)</span></span>\
<span data-ttu-id="b39e5-334">シリアル化を実行するコードを記述する際に従う必要がある、安全なコーディングのガイドラインについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b39e5-334">Describes the secure coding guidelines to follow when writing code that performs serialization.</span></span>

- <span data-ttu-id="b39e5-335">[NET リモート処理](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b39e5-335">[.NET Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100))</span></span>\
<span data-ttu-id="b39e5-336">リモート通信用の .NET Framework で開始するさまざまな方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b39e5-336">Describes the various methods Starting in .NET Framework for remote communications.</span></span>

- <span data-ttu-id="b39e5-337">[ASP.NETおよび XML Web サービス クライアントを使用して作成される XML Web サービス](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b39e5-337">[XML Web Services Created Using ASP.NET and XML Web Service Clients](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span></span>\
<span data-ttu-id="b39e5-338">ASP.NETを使用して作成された XML Web サービスをプログラミングする方法について説明する記事です。</span><span class="sxs-lookup"><span data-stu-id="b39e5-338">Articles that describe and explain how to program XML Web services created using ASP.NET.</span></span>
