---
title: IMetaDataDispenser::DefineScope メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.DefineScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::DefineScope
helpviewer_keywords:
- DefineScope method [.NET Framework metadata]
- IMetaDataDispenser::DefineScope method [.NET Framework metadata]
ms.assetid: af28db02-29af-45ac-aec6-8d6c6123c2ff
topic_type:
- apiref
ms.openlocfilehash: 2f9325f3795262a0c33af02f87fc5d3a020658cf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177641"
---
# <a name="imetadatadispenserdefinescope-method"></a><span data-ttu-id="3a077-102">IMetaDataDispenser::DefineScope メソッド</span><span class="sxs-lookup"><span data-stu-id="3a077-102">IMetaDataDispenser::DefineScope Method</span></span>
<span data-ttu-id="3a077-103">新しいメタデータを作成できる領域をメモリ内に作成します。</span><span class="sxs-lookup"><span data-stu-id="3a077-103">Creates a new area in memory in which you can create new metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a077-104">構文</span><span class="sxs-lookup"><span data-stu-id="3a077-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineScope (  
    [in]  REFCLSID    rclsid,  
    [in]  DWORD       dwCreateFlags,  
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a077-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3a077-105">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="3a077-106">[in]作成するメタデータ構造のバージョンの CLSID。</span><span class="sxs-lookup"><span data-stu-id="3a077-106">[in] The CLSID of the version of metadata structures to be created.</span></span> <span data-ttu-id="3a077-107">この値は、.NET Framework バージョン 2.0 のCLSID_CorMetaDataRuntimeする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a077-107">This value must be CLSID_CorMetaDataRuntime for the .NET Framework version 2.0.</span></span>  
  
 `dwCreateFlags`  
 <span data-ttu-id="3a077-108">[in]オプションを指定するフラグ。</span><span class="sxs-lookup"><span data-stu-id="3a077-108">[in] Flags that specify options.</span></span> <span data-ttu-id="3a077-109">この値は、.NET Framework 2.0 の場合は 0 である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a077-109">This value must be zero for the .NET Framework 2.0.</span></span>  
  
 `riid`  
 <span data-ttu-id="3a077-110">[in]返される必要なメタデータ インターフェイスの IID。呼び出し元は、インターフェイスを使用して新しいメタデータを作成します。</span><span class="sxs-lookup"><span data-stu-id="3a077-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to create the new metadata.</span></span>  
  
 <span data-ttu-id="3a077-111">の値は`riid`、"emit"インタフェースの1つを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a077-111">The value of `riid` must specify one of the "emit" interfaces.</span></span> <span data-ttu-id="3a077-112">有効な値は、IID_IMetaDataEmit、IID_IMetaDataAssemblyEmit、またはIID_IMetaDataEmit2です。</span><span class="sxs-lookup"><span data-stu-id="3a077-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit, or IID_IMetaDataEmit2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="3a077-113">[アウト]返されたインターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3a077-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a077-114">解説</span><span class="sxs-lookup"><span data-stu-id="3a077-114">Remarks</span></span>  
 <span data-ttu-id="3a077-115">`DefineScope`インメモリ メタデータ テーブルのセットを作成し、メタデータの一意の GUID (モジュール バージョン識別子、または MVID) を生成し、生成されるコンパイル 単位のモジュール テーブルにエントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="3a077-115">`DefineScope` creates a set of in-memory metadata tables, generates a unique GUID (module version identifier, or MVID) for the metadata, and creates an entry in the module table for the compilation unit being emitted.</span></span>  
  
 <span data-ttu-id="3a077-116">必要に応じて[、IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md)または[IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md)メソッドを使用して、メタデータ スコープ全体に属性をアタッチできます。</span><span class="sxs-lookup"><span data-stu-id="3a077-116">You can attach attributes to the metadata scope as a whole by using the [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) or [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) method, as appropriate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a077-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="3a077-117">Requirements</span></span>  
 <span data-ttu-id="3a077-118">**プラットフォーム:**[「システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a077-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a077-119">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="3a077-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3a077-120">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="3a077-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3a077-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a077-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a077-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a077-122">See also</span></span>

- [<span data-ttu-id="3a077-123">IMetaDataDispenser インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3a077-123">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="3a077-124">IMetaDataDispenserEx インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3a077-124">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="3a077-125">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3a077-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="3a077-126">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3a077-126">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="3a077-127">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3a077-127">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
