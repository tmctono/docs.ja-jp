---
title: バイナリ シリアル化
description: この記事では、バイナリ シリアル化と .NET Core でそれがサポートされている型について説明します。 バイナリ シリアル化の危険性とその代替手段に注意してください。
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
ms.openlocfilehash: 4ed76437b743da842d6ba07d29fe7985f824abf0
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421281"
---
# <a name="binary-serialization"></a><span data-ttu-id="3ed76-104">バイナリ シリアル化</span><span class="sxs-lookup"><span data-stu-id="3ed76-104">Binary serialization</span></span>

<span data-ttu-id="3ed76-105">シリアル化は、オブジェクトの状態をストレージ メディアに格納するプロセスとして定義することができます。</span><span class="sxs-lookup"><span data-stu-id="3ed76-105">Serialization can be defined as the process of storing the state of an object to a storage medium.</span></span> <span data-ttu-id="3ed76-106">このプロセスの実行中に、オブジェクトのパブリックおよびプライベートなフィールドとクラス (クラスを格納しているアセンブリを含む) の名前がバイト ストリームに変換され、データ ストリームに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="3ed76-106">During this process, the public and private fields of the object and the name of the class, including the assembly containing the class, are converted to a stream of bytes, which is then written to a data stream.</span></span> <span data-ttu-id="3ed76-107">続いてオブジェクトが逆シリアル化され、元のオブジェクトの完全な複製が作成されます。</span><span class="sxs-lookup"><span data-stu-id="3ed76-107">When the object is subsequently deserialized, an exact clone of the original object is created.</span></span>

<span data-ttu-id="3ed76-108">オブジェクト指向環境でシリアル化機構を実装する場合は、使いやすさと柔軟性の間での数多くのトレードオフについて考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ed76-108">When implementing a serialization mechanism in an object-oriented environment, you have to make a number of tradeoffs between ease of use and flexibility.</span></span> <span data-ttu-id="3ed76-109">プロセスを十分に制御できる場合は、プロセスの大部分を自動化できます。</span><span class="sxs-lookup"><span data-stu-id="3ed76-109">The process can be automated to a large extent, provided you are given sufficient control over the process.</span></span> <span data-ttu-id="3ed76-110">たとえば、単純なバイナリ シリアル化では不十分な状況が発生する場合や、シリアル化が必要なクラス内のフィールドを決定するだけの明確な理由がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="3ed76-110">For example, situations may arise where simple binary serialization is not sufficient, or there might be a specific reason to decide which fields in a class need to be serialized.</span></span> <span data-ttu-id="3ed76-111">以下のセクションでは、.NET に用意されている堅牢なシリアル化機構について検討し、必要に応じてプロセスをカスタマイズするためのいくつかの重要な機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="3ed76-111">The following sections examine the robust serialization mechanism provided with .NET and highlight a number of important features that allow you to customize the process to meet your needs.</span></span>

> [!NOTE]
> <span data-ttu-id="3ed76-112">オブジェクトのシリアル化と逆シリアル化を行う際に使用した .NET Framework のバージョンが異なる場合、UTF-8 または UTF-7 でエンコードされたオブジェクトの状態は保持されません。</span><span class="sxs-lookup"><span data-stu-id="3ed76-112">The state of a UTF-8 or UTF-7 encoded object is not preserved if the object is serialized and deserialized using different .NET Framework versions.</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

<span data-ttu-id="3ed76-113">バイナリ シリアル化を使用すると、オブジェクト内のプライベート メンバーを変更することで、その状態を変更できます。</span><span class="sxs-lookup"><span data-stu-id="3ed76-113">Binary serialization allows modifying private members inside an object and therefore changing the state of it.</span></span> <span data-ttu-id="3ed76-114">このため、パブリック API サーフェイスで動作する他のシリアル化フレームワーク (<xref:System.Text.Json?displayProperty=fullName> など) をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3ed76-114">Because of this, other serialization frameworks, like <xref:System.Text.Json?displayProperty=fullName>, that operate on the public API surface are recommended.</span></span>

## <a name="net-core"></a><span data-ttu-id="3ed76-115">.NET Core</span><span class="sxs-lookup"><span data-stu-id="3ed76-115">.NET Core</span></span>

<span data-ttu-id="3ed76-116">.NET Core では、型のサブセットに対してバイナリ シリアル化がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3ed76-116">.NET Core supports binary serialization for a subset of types.</span></span> <span data-ttu-id="3ed76-117">サポートされている型の一覧は、以下の「[シリアル化可能な型](#serializable-types)」セクションで確認できます。</span><span class="sxs-lookup"><span data-stu-id="3ed76-117">You can see the list of supported types in the [Serializable types](#serializable-types) section that follows.</span></span> <span data-ttu-id="3ed76-118">一覧表示されている型は、.NET Framework 4.5.1 以降のバージョン間と .NET Core 2.0 以降のバージョン間でシリアル化できることが保証されていいます。</span><span class="sxs-lookup"><span data-stu-id="3ed76-118">The listed types are guaranteed to be serializable between .NET Framework 4.5.1 and later versions and between .NET Core 2.0 and later versions.</span></span> <span data-ttu-id="3ed76-119">Mono などのその他の .NET 実装は公式にサポートされていませんが、同じく機能するはずです。</span><span class="sxs-lookup"><span data-stu-id="3ed76-119">Other .NET implementations, such as Mono, aren't officially supported but should also work.</span></span>

### <a name="serializable-types"></a><span data-ttu-id="3ed76-120">シリアル化可能な型</span><span class="sxs-lookup"><span data-stu-id="3ed76-120">Serializable types</span></span>

> [!div class="mx-tdCol2BreakAll"]
> | <span data-ttu-id="3ed76-121">種類</span><span class="sxs-lookup"><span data-stu-id="3ed76-121">Type</span></span> | <span data-ttu-id="3ed76-122">メモ</span><span class="sxs-lookup"><span data-stu-id="3ed76-122">Notes</span></span> |
> | - | - |
> | <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-123">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-123">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderInternalCompilerException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-124">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-124">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AccessViolationException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-125">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-125">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AggregateException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-126">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-126">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AppDomainUnloadedException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-127">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-127">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ApplicationException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-128">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-128">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-129">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-129">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentNullException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-130">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-130">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentOutOfRangeException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-131">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-131">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArithmeticException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-132">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-132">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Array?displayProperty=nameWithType> | |
> | <xref:System.ArraySegment%601?displayProperty=nameWithType> | |
> | <xref:System.ArrayTypeMismatchException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-133">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-133">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Attribute?displayProperty=nameWithType> | |
> | <xref:System.BadImageFormatException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-134">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-134">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Boolean?displayProperty=nameWithType> | |
> | <xref:System.Byte?displayProperty=nameWithType> | |
> | <xref:System.CannotUnloadAppDomainException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-135">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-135">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Char?displayProperty=nameWithType> | |
> | <xref:System.Collections.ArrayList?displayProperty=nameWithType> | |
> | <xref:System.Collections.BitArray?displayProperty=nameWithType> | |
> | <xref:System.Collections.Comparer?displayProperty=nameWithType> | |
> | <xref:System.Collections.DictionaryEntry?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Comparer%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.EqualityComparer%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.HashSet%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-136">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-136">Starting in .NET Core 2.0.4.</span></span> |
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
> | `System.Collections.Generic.NonRandomizedStringEqualityComparer` | <span data-ttu-id="3ed76-137">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-137">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.BindingList%601?displayProperty=nameWithType> | |
> | <xref:System.ComponentModel.DataAnnotations.ValidationException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-138">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-138">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.Design.CheckoutException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-139">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-139">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.InvalidAsynchronousStateException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-140">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-140">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.InvalidEnumArgumentException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-141">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-141">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.LicenseException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-142">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-142">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="3ed76-143">.NET Framework から .NET Core へのシリアル化はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3ed76-143">Serialization from .NET Framework to .NET Core is not supported.</span></span> |
> | <xref:System.ComponentModel.WarningException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-144">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-144">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.Win32Exception?displayProperty=nameWithType> | <span data-ttu-id="3ed76-145">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-145">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.ConfigurationErrorsException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-146">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-146">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.ConfigurationException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-147">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-147">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.Provider.ProviderException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-148">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-148">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyIsReadOnlyException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-149">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-149">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-150">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-150">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyWrongTypeException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-151">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-151">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ContextMarshalException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-152">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-152">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DBNull?displayProperty=nameWithType> | <span data-ttu-id="3ed76-153">.NET Core 2.0.2 以降のバージョンから。</span><span class="sxs-lookup"><span data-stu-id="3ed76-153">Starting in .NET Core 2.0.2 and later versions.</span></span> |
> | <xref:System.Data.Common.DbException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-154">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-154">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.ConstraintException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-155">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-155">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DBConcurrencyException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-156">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-156">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DataException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-157">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-157">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DataSet?displayProperty=nameWithType> | |
> | <xref:System.Data.DataTable?displayProperty=nameWithType> | <span data-ttu-id="3ed76-158">`RemotingFormat` を `SerializationFormat.Binary` に設定する場合は、.NET Core 2.1 以降のバージョンとのみ交換できます。</span><span class="sxs-lookup"><span data-stu-id="3ed76-158">If you set `RemotingFormat` to `SerializationFormat.Binary`, it can only be exchanged with .NET Core 2.1 and later versions.</span></span> |
> | <xref:System.Data.DeletedRowInaccessibleException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-159">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-159">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DuplicateNameException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-160">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-160">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.EvaluateException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-161">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-161">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InRowChangingEventException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-162">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-162">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InvalidConstraintException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-163">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-163">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InvalidExpressionException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-164">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-164">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.MissingPrimaryKeyException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-165">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-165">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.NoNullAllowedException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-166">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-166">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.Odbc.OdbcException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-167">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-167">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.OperationAbortedException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-168">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-168">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.PropertyCollection?displayProperty=nameWithType> | |
> | <xref:System.Data.ReadOnlyException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-169">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-169">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.RowNotInTableException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-170">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-170">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlClient.SqlException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-171">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-171">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="3ed76-172">.NET Framework から .NET Core へのシリアル化はサポートされていません</span><span class="sxs-lookup"><span data-stu-id="3ed76-172">Serialization from .NET Framework to .NET Core is not supported</span></span> |
> | <xref:System.Data.SqlTypes.SqlAlreadyFilledException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-173">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-173">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlBoolean?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlByte?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlDateTime?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlDouble?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlGuid?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt16?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt32?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt64?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlNotFilledException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-174">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-174">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlNullValueException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-175">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-175">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlString?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlTruncateException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-176">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-176">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlTypeException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-177">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-177">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.StrongTypingException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-178">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-178">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SyntaxErrorException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-179">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-179">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.VersionNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-180">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-180">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DataMisalignedException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-181">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-181">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DateTime?displayProperty=nameWithType> | |
> | <xref:System.DateTimeOffset?displayProperty=nameWithType> | |
> | <xref:System.Decimal?displayProperty=nameWithType> | |
> | `System.Diagnostics.Contracts.ContractException` | <span data-ttu-id="3ed76-182">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-182">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Diagnostics.Tracing.EventSourceException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-183">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-183">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.DirectoryNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-184">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-184">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.MultipleMatchesException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-185">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-185">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.NoMatchingPrincipalException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-186">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-186">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PasswordException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-187">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-187">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-188">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-188">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalExistsException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-189">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-189">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalOperationException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-190">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-190">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalServerDownException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-191">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-191">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectExistsException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-192">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-192">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-193">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-193">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryOperationException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-194">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-194">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryServerDownException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-195">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-195">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ForestTrustCollisionException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-196">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-196">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.SyncFromAllServersOperationException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-197">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-197">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.DirectoryServicesCOMException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-198">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-198">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.BerConversionException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-199">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-199">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.DirectoryException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-200">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-200">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.DirectoryOperationException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-201">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-201">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.LdapException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-202">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-202">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.TlsOperationException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-203">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-203">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DivideByZeroException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-204">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-204">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DllNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-205">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-205">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Double?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Color?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Point?displayProperty=nameWithType> | |
> | <xref:System.Drawing.PointF?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Rectangle?displayProperty=nameWithType> | |
> | <xref:System.Drawing.RectangleF?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Size?displayProperty=nameWithType> | |
> | <xref:System.Drawing.SizeF?displayProperty=nameWithType> | |
> | <xref:System.DuplicateWaitObjectException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-206">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-206">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.EntryPointNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-207">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-207">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Enum?displayProperty=nameWithType> | |
> | <xref:System.EventArgs?displayProperty=nameWithType> | <span data-ttu-id="3ed76-208">.NET Core 2.0.6 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-208">Starting in .NET Core 2.0.6.</span></span> |
> | <xref:System.Exception?displayProperty=nameWithType> | |
> | <xref:System.ExecutionEngineException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-209">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-209">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.FieldAccessException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-210">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-210">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.FormatException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-211">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-211">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> | |
> | <xref:System.Globalization.CultureNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-212">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-212">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Globalization.SortVersion?displayProperty=nameWithType> | |
> | <xref:System.Guid?displayProperty=nameWithType> | |
> | `System.IO.Compression.ZLibException` | <span data-ttu-id="3ed76-213">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-213">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.DriveNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-214">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-214">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.EndOfStreamException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-215">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-215">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileFormatException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-216">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-216">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileLoadException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-217">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-217">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-218">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-218">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.IOException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-219">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-219">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.InternalBufferOverflowException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-220">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-220">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.InvalidDataException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-221">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-221">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.IsolatedStorage.IsolatedStorageException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-222">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-222">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.PathTooLongException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-223">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-223">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IndexOutOfRangeException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-224">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-224">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InsufficientExecutionStackException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-225">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-225">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InsufficientMemoryException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-226">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-226">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Int16?displayProperty=nameWithType> | |
> | <xref:System.Int32?displayProperty=nameWithType> | |
> | <xref:System.Int64?displayProperty=nameWithType> | |
> | <xref:System.IntPtr?displayProperty=nameWithType> | |
> | <xref:System.InvalidCastException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-227">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-227">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidOperationException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-228">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-228">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidProgramException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-229">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-229">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidTimeZoneException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-230">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-230">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MemberAccessException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-231">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-231">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MethodAccessException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-232">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-232">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingFieldException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-233">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-233">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingMemberException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-234">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-234">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingMethodException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-235">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-235">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MulticastNotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-236">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-236">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Cookie?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieCollection?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieContainer?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-237">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-237">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.HttpListenerException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-238">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-238">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-239">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-239">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpFailedRecipientException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-240">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-240">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpFailedRecipientsException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-241">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-241">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.NetworkInformation.NetworkInformationException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-242">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-242">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.NetworkInformation.PingException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-243">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-243">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.ProtocolViolationException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-244">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-244">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Sockets.SocketException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-245">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-245">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.WebException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-246">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-246">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.WebSockets.WebSocketException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-247">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-247">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotFiniteNumberException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-248">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-248">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotImplementedException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-249">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-249">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-250">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-250">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NullReferenceException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-251">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-251">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Nullable%601?displayProperty=nameWithType> | |
> | <xref:System.Numerics.BigInteger?displayProperty=nameWithType> | |
> | <xref:System.Numerics.Complex?displayProperty=nameWithType> | |
> | <xref:System.Object?displayProperty=nameWithType> | |
> | <xref:System.ObjectDisposedException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-252">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-252">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OperationCanceledException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-253">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-253">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OutOfMemoryException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-254">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-254">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OverflowException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-255">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-255">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.PlatformNotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-256">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-256">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.RankException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-257">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-257">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.AmbiguousMatchException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-258">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-258">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.CustomAttributeFormatException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-259">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-259">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.InvalidFilterCriteriaException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-260">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-260">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.ReflectionTypeLoadException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-261">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-261">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="3ed76-262">.NET Framework から .NET Core へのシリアル化はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3ed76-262">Serialization from .NET Framework to .NET Core is not supported.</span></span> |
> | <xref:System.Reflection.TargetException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-263">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-263">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.TargetInvocationException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-264">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-264">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.TargetParameterCountException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-265">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-265">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Resources.MissingManifestResourceException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-266">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-266">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Resources.MissingSatelliteAssemblyException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-267">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-267">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.CompilerServices.RuntimeWrappedException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-268">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-268">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.COMException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-269">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-269">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.ExternalException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-270">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-270">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.InvalidComObjectException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-271">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-271">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.InvalidOleVariantTypeException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-272">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-272">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.MarshalDirectiveException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-273">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-273">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SEHException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-274">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-274">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-275">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-275">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-276">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-276">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.Serialization.InvalidDataContractException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-277">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-277">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.Serialization.SerializationException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-278">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-278">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.SByte?displayProperty=nameWithType> | |
> | <xref:System.Security.AccessControl.PrivilegeNotHeldException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-279">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-279">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Authentication.AuthenticationException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-280">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-280">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Authentication.InvalidCredentialException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-281">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-281">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Cryptography.CryptographicException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-282">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-282">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Cryptography.CryptographicUnexpectedOperationException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-283">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-283">Starting in .NET Core 2.0.4.</span></span> |
> | `System.Security.Cryptography.Xml.CryptoSignedXmlRecursionException` | <span data-ttu-id="3ed76-284">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-284">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.HostProtectionException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-285">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-285">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Policy.PolicyException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-286">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-286">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Principal.IdentityNotMappedException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-287">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-287">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.SecurityException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-288">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-288">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="3ed76-289">シリアル化データが制限されます。</span><span class="sxs-lookup"><span data-stu-id="3ed76-289">Limited serialization data.</span></span> |
> | <xref:System.Security.VerificationException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-290">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-290">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.XmlSyntaxException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-291">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-291">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ServiceProcess.TimeoutException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-292">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-292">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Single?displayProperty=nameWithType> | |
> | <xref:System.StackOverflowException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-293">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-293">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.String?displayProperty=nameWithType> | |
> | <xref:System.StringComparer?displayProperty=nameWithType> | |
> | <xref:System.SystemException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-294">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-294">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.DecoderFallbackException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-295">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-295">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.EncoderFallbackException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-296">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-296">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.RegularExpressions.RegexMatchTimeoutException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-297">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-297">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.StringBuilder?displayProperty=nameWithType> | |
> | <xref:System.Threading.AbandonedMutexException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-298">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-298">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.BarrierPostPhaseException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-299">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-299">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.LockRecursionException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-300">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-300">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.SemaphoreFullException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-301">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-301">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.SynchronizationLockException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-302">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-302">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.Tasks.TaskCanceledException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-303">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-303">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.Tasks.TaskSchedulerException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-304">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-304">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadAbortException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-305">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-305">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadInterruptedException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-306">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-306">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadStartException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-307">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-307">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadStateException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-308">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-308">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.WaitHandleCannotBeOpenedException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-309">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-309">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TimeSpan?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneInfo.AdjustmentRule?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneInfo?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-310">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-310">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TimeoutException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-311">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-311">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionAbortedException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-312">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-312">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-313">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-313">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionInDoubtException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-314">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-314">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionManagerCommunicationException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-315">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-315">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionPromotionException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-316">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-316">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Tuple?displayProperty=nameWithType> | |
> | <xref:System.TypeAccessException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-317">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-317">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeInitializationException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-318">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-318">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeLoadException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-319">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-319">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeUnloadedException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-320">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-320">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.UInt16?displayProperty=nameWithType> | |
> | <xref:System.UInt32?displayProperty=nameWithType> | |
> | <xref:System.UInt64?displayProperty=nameWithType> | |
> | <xref:System.UIntPtr?displayProperty=nameWithType> | |
> | <xref:System.UnauthorizedAccessException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-321">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-321">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Uri?displayProperty=nameWithType> | |
> | <xref:System.UriFormatException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-322">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-322">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ValueTuple?displayProperty=nameWithType> | <span data-ttu-id="3ed76-323">.NET Framework 4.7 以前のバージョンではシリアル化できません。</span><span class="sxs-lookup"><span data-stu-id="3ed76-323">Not serializable in .NET Framework 4.7 and earlier versions.</span></span> |
> | <xref:System.ValueType?displayProperty=nameWithType> | |
> | <xref:System.Version?displayProperty=nameWithType> | |
> | <xref:System.WeakReference%601?displayProperty=nameWithType> | |
> | <xref:System.WeakReference?displayProperty=nameWithType> | |
> | <xref:System.Xml.Schema.XmlSchemaException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-324">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-324">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Schema.XmlSchemaInferenceException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-325">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-325">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Schema.XmlSchemaValidationException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-326">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-326">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.XPath.XPathException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-327">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-327">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.XmlException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-328">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-328">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Xsl.XsltCompileException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-329">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-329">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Xsl.XsltException?displayProperty=nameWithType> | <span data-ttu-id="3ed76-330">.NET Core 2.0.4 以降。</span><span class="sxs-lookup"><span data-stu-id="3ed76-330">Starting in .NET Core 2.0.4.</span></span> |

## <a name="see-also"></a><span data-ttu-id="3ed76-331">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ed76-331">See also</span></span>

- <xref:System.Runtime.Serialization>\
<span data-ttu-id="3ed76-332">オブジェクトのシリアル化と逆シリアル化に使用できるクラスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3ed76-332">Contains classes that can be used for serializing and deserializing objects.</span></span>

- <span data-ttu-id="3ed76-333">[XML シリアル化および SOAP シリアル化](../../../docs/standard/serialization/xml-and-soap-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="3ed76-333">[XML and SOAP Serialization](../../../docs/standard/serialization/xml-and-soap-serialization.md)</span></span>\
<span data-ttu-id="3ed76-334">共通言語ランタイムに付属している XML シリアル化機構について説明します。</span><span class="sxs-lookup"><span data-stu-id="3ed76-334">Describes the XML serialization mechanism that is included with the common language runtime.</span></span>

- <span data-ttu-id="3ed76-335">[セキュリティとシリアル化](../../../docs/framework/misc/security-and-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="3ed76-335">[Security and Serialization](../../../docs/framework/misc/security-and-serialization.md)</span></span>\
<span data-ttu-id="3ed76-336">シリアル化を実行するコードを記述する際に従う必要がある、安全なコーディングのガイドラインについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3ed76-336">Describes the secure coding guidelines to follow when writing code that performs serialization.</span></span>

- <span data-ttu-id="3ed76-337">[.NET リモート処理](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="3ed76-337">[.NET Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100))</span></span>\
<span data-ttu-id="3ed76-338">.NET Framework で開始されたリモート通信のためのさまざまな方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3ed76-338">Describes the various methods Starting in .NET Framework for remote communications.</span></span>

- <span data-ttu-id="3ed76-339">[ASP.NET と XML Web サービス クライアントを使用して作成した XML Web サービス](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="3ed76-339">[XML Web Services Created Using ASP.NET and XML Web Service Clients](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span></span>\
<span data-ttu-id="3ed76-340">ASP.NET を使用して作成する XML Web サービスのプログラミング方法について説明した記事です。</span><span class="sxs-lookup"><span data-stu-id="3ed76-340">Articles that describe and explain how to program XML Web services created using ASP.NET.</span></span>
