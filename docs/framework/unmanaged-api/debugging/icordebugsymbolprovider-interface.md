---
title: ICorDebugSymbolProvider インターフェイス
ms.date: 03/30/2017
ms.assetid: 85b24196-b6c6-4bda-9de3-47180bd6ff96
ms.openlocfilehash: 6f7a8a2b12c047b956a3b6e85fe8365e0360b3f2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791528"
---
# <a name="icordebugsymbolprovider-interface"></a><span data-ttu-id="f3c7d-102">ICorDebugSymbolProvider インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f3c7d-102">ICorDebugSymbolProvider Interface</span></span>
<span data-ttu-id="f3c7d-103">デバッグ シンボル情報を取得するために使用できるメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="f3c7d-103">Provides methods that can be used to retrieve debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f3c7d-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="f3c7d-104">Methods</span></span>  
  
|<span data-ttu-id="f3c7d-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="f3c7d-105">Method</span></span>|<span data-ttu-id="f3c7d-106">説明</span><span class="sxs-lookup"><span data-stu-id="f3c7d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f3c7d-107">GetAssemblyImageBytes メソッド</span><span class="sxs-lookup"><span data-stu-id="f3c7d-107">GetAssemblyImageBytes Method</span></span>](icordebugsymbolprovider-getassemblyimagebytes-method.md)|<span data-ttu-id="f3c7d-108">マージされたアセンブリ内の指定の相対仮想アドレス (RVA: relative virtual address) で、マージされたアセンブリのデータを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="f3c7d-108">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>|  
|[<span data-ttu-id="f3c7d-109">GetAssemblyImageMetadata メソッド</span><span class="sxs-lookup"><span data-stu-id="f3c7d-109">GetAssemblyImageMetadata Method</span></span>](icordebugsymbolprovider-getassemblyimagemetadata-method.md)|<span data-ttu-id="f3c7d-110">マージされたアセンブリのメタデータを返します。</span><span class="sxs-lookup"><span data-stu-id="f3c7d-110">Returns the metadata from a merged assembly.</span></span>|  
|[<span data-ttu-id="f3c7d-111">GetCodeRange メソッド</span><span class="sxs-lookup"><span data-stu-id="f3c7d-111">GetCodeRange Method</span></span>](icordebugsymbolprovider-getcoderange-method.md)|<span data-ttu-id="f3c7d-112">メソッド内の指定の相対仮想アドレス (RVA: relative virtual address) で、メソッド開始アドレスとサイズを取得します。</span><span class="sxs-lookup"><span data-stu-id="f3c7d-112">Gets the method start address and size given a relative virtual address (RVA) in a method.</span></span>|  
|[<span data-ttu-id="f3c7d-113">GetInstanceFieldSymbols メソッド</span><span class="sxs-lookup"><span data-stu-id="f3c7d-113">GetInstanceFieldSymbols Method</span></span>](icordebugsymbolprovider-getinstancefieldsymbols-method.md)|<span data-ttu-id="f3c7d-114">typespec シグネチャに対応するインスタンス フィールド シンボルを取得します。</span><span class="sxs-lookup"><span data-stu-id="f3c7d-114">Gets the instance field symbols that correspond to a typespec signature.</span></span>|  
|[<span data-ttu-id="f3c7d-115">GetMergedAssemblyRecords メソッド</span><span class="sxs-lookup"><span data-stu-id="f3c7d-115">GetMergedAssemblyRecords Method</span></span>](icordebugsymbolprovider-getmergedassemblyrecords-method.md)|<span data-ttu-id="f3c7d-116">すべてのマージされたアセンブリのシンボル レコードを取得します。</span><span class="sxs-lookup"><span data-stu-id="f3c7d-116">Gets the symbol records for all the merged assemblies.</span></span>|  
|[<span data-ttu-id="f3c7d-117">GetMethodLocalSymbols メソッド</span><span class="sxs-lookup"><span data-stu-id="f3c7d-117">GetMethodLocalSymbols Method</span></span>](icordebugsymbolprovider-getmethodlocalsymbols-method.md)|<span data-ttu-id="f3c7d-118">メソッドの指定の相対仮想アドレス (RVA) で、そのメソッドのローカル シンボルを取得します。</span><span class="sxs-lookup"><span data-stu-id="f3c7d-118">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>|  
|[<span data-ttu-id="f3c7d-119">GetMethodParameterSymbols メソッド</span><span class="sxs-lookup"><span data-stu-id="f3c7d-119">GetMethodParameterSymbols Method</span></span>](icordebugsymbolprovider-getmethodparametersymbols-method.md)|<span data-ttu-id="f3c7d-120">メソッドの指定の相対仮想アドレス (RVA: relative virtual address ) で、そのメソッドのパラメーター シンボルを取得します。</span><span class="sxs-lookup"><span data-stu-id="f3c7d-120">Gets a method's parameter symbols given the relative virtual address (RVA) of that method.</span></span>|  
|[<span data-ttu-id="f3c7d-121">GetMethodProps メソッド</span><span class="sxs-lookup"><span data-stu-id="f3c7d-121">GetMethodProps Method</span></span>](icordebugsymbolprovider-getmethodprops-method.md)|<span data-ttu-id="f3c7d-122">メソッドの指定の相対仮想アドレス (RVA) で、そのメソッドのプロパティに関する情報 (メソッドのメタデータ トークンなど) と、そのジェネリック パラメーターに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="f3c7d-122">Returns information about method properties, such as the method's metadata token and information about its generic parameters, given a relative virtual address (RVA) in that method.</span></span>|  
|[<span data-ttu-id="f3c7d-123">GetObjectSize メソッド</span><span class="sxs-lookup"><span data-stu-id="f3c7d-123">GetObjectSize Method</span></span>](icordebugsymbolprovider-getobjectsize-method.md)|<span data-ttu-id="f3c7d-124">typespec シグネチャに基づいてオブジェクトのオブジェクト サイズを返します。</span><span class="sxs-lookup"><span data-stu-id="f3c7d-124">Returns the object size for an object based on its typespec signature.</span></span>|  
|[<span data-ttu-id="f3c7d-125">GetStaticFieldSymbols メソッド</span><span class="sxs-lookup"><span data-stu-id="f3c7d-125">GetStaticFieldSymbols Method</span></span>](icordebugsymbolprovider-getstaticfieldsymbols-method.md)|<span data-ttu-id="f3c7d-126">typespec シグネチャに対応する静的フィールド シンボルを取得します。</span><span class="sxs-lookup"><span data-stu-id="f3c7d-126">Gets the static field symbols that correspond to a typespec signature.</span></span>|  
|[<span data-ttu-id="f3c7d-127">GetTypeProps メソッド</span><span class="sxs-lookup"><span data-stu-id="f3c7d-127">GetTypeProps Method</span></span>](icordebugsymbolprovider-gettypeprops-method.md)|<span data-ttu-id="f3c7d-128">Vtable の指定の相対仮想アドレス (RVA) における、ジェネリック パラメーターのシグネチャの数などの型のプロパティに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="f3c7d-128">Returns information about a type's properties, such as the number of signature of its generic parameters, given a relative virtual address (RVA) in a vtable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3c7d-129">コメント</span><span class="sxs-lookup"><span data-stu-id="f3c7d-129">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f3c7d-130">このインターフェイスは .NET ネイティブでのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="f3c7d-130">This interface is available with .NET Native only.</span></span> <span data-ttu-id="f3c7d-131">.NET ネイティブの外部で ICorDebug シナリオについてこのインターフェイスを実装する場合は、共通言語ランタイムはこのインターフェイスを無視します。</span><span class="sxs-lookup"><span data-stu-id="f3c7d-131">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3c7d-132">要件</span><span class="sxs-lookup"><span data-stu-id="f3c7d-132">Requirements</span></span>  
 <span data-ttu-id="f3c7d-133">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3c7d-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3c7d-134">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f3c7d-134">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f3c7d-135">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3c7d-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3c7d-136">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3c7d-136">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3c7d-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="f3c7d-137">See also</span></span>

- [<span data-ttu-id="f3c7d-138">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f3c7d-138">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="f3c7d-139">デバッグ</span><span class="sxs-lookup"><span data-stu-id="f3c7d-139">Debugging</span></span>](index.md)
