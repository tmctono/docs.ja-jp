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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 76a439effad9cb3f6dcdd232590cf2196ee7ab99
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62044397"
---
# <a name="imetadatadispenserdefinescope-method"></a><span data-ttu-id="34779-102">IMetaDataDispenser::DefineScope メソッド</span><span class="sxs-lookup"><span data-stu-id="34779-102">IMetaDataDispenser::DefineScope Method</span></span>
<span data-ttu-id="34779-103">メモリの新しいメタデータを作成するには、新しい領域を作成します。</span><span class="sxs-lookup"><span data-stu-id="34779-103">Creates a new area in memory in which you can create new metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34779-104">構文</span><span class="sxs-lookup"><span data-stu-id="34779-104">Syntax</span></span>  
  
```  
HRESULT DefineScope (  
    [in]  REFCLSID    rclsid,  
    [in]  DWORD       dwCreateFlags,  
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34779-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="34779-105">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="34779-106">[in]作成するメタデータ構造体のバージョンの CLSID。</span><span class="sxs-lookup"><span data-stu-id="34779-106">[in] The CLSID of the version of metadata structures to be created.</span></span> <span data-ttu-id="34779-107">この値は、.NET Framework version 2.0 の CLSID_CorMetaDataRuntime を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34779-107">This value must be CLSID_CorMetaDataRuntime for the .NET Framework version 2.0.</span></span>  
  
 `dwCreateFlags`  
 <span data-ttu-id="34779-108">[in]オプションを指定するフラグ。</span><span class="sxs-lookup"><span data-stu-id="34779-108">[in] Flags that specify options.</span></span> <span data-ttu-id="34779-109">この値は、.NET Framework 2.0 の 0 にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="34779-109">This value must be zero for the .NET Framework 2.0.</span></span>  
  
 `riid`  
 <span data-ttu-id="34779-110">[in]返される必要なメタデータ インターフェイスの IID呼び出し元はインターフェイスを使用して、新しいメタデータを作成します。</span><span class="sxs-lookup"><span data-stu-id="34779-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to create the new metadata.</span></span>  
  
 <span data-ttu-id="34779-111">値`riid`「生成」インターフェイスのいずれかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34779-111">The value of `riid` must specify one of the "emit" interfaces.</span></span> <span data-ttu-id="34779-112">有効な値は IID_IMetaDataEmit、IID_IMetaDataAssemblyEmit、または IID_IMetaDataEmit2 です。</span><span class="sxs-lookup"><span data-stu-id="34779-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit, or IID_IMetaDataEmit2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="34779-113">[out]返されたインターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="34779-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34779-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="34779-114">Remarks</span></span>  
 <span data-ttu-id="34779-115">`DefineScope` メモリ内のメタデータ テーブルのセットを作成し、メタデータの一意の GUID (モジュールのバージョンの識別子、または MVID) が生成されますが生成するコンパイル単位の module テーブル エントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="34779-115">`DefineScope` creates a set of in-memory metadata tables, generates a unique GUID (module version identifier, or MVID) for the metadata, and creates an entry in the module table for the compilation unit being emitted.</span></span>  
  
 <span data-ttu-id="34779-116">使用して、全体としてのメタデータ スコープの属性をアタッチすることができます、 [imetadataemit::setmoduleprops](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md)または[imetadataemit::definecustomattribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md)として適切なメソッドです。</span><span class="sxs-lookup"><span data-stu-id="34779-116">You can attach attributes to the metadata scope as a whole by using the [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) or [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) method, as appropriate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34779-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="34779-117">Requirements</span></span>  
 <span data-ttu-id="34779-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="34779-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34779-119">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="34779-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="34779-120">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="34779-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="34779-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34779-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34779-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="34779-122">See also</span></span>

- [<span data-ttu-id="34779-123">IMetaDataDispenser インターフェイス</span><span class="sxs-lookup"><span data-stu-id="34779-123">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="34779-124">IMetaDataDispenserEx インターフェイス</span><span class="sxs-lookup"><span data-stu-id="34779-124">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="34779-125">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="34779-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="34779-126">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="34779-126">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="34779-127">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="34779-127">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
