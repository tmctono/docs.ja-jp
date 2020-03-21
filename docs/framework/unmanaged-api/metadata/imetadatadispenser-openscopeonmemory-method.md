---
title: IMetaDataDispenser::OpenScopeOnMemory メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.OpenScopeOnMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScopeOnMemory
helpviewer_keywords:
- OpenScopeOnMemory method [.NET Framework metadata]
- IMetaDataDispenser::OpenScopeOnMemory method [.NET Framework metadata]
ms.assetid: 14218249-bdec-48ae-b5fc-9f57f7ca8501
topic_type:
- apiref
ms.openlocfilehash: 492c37540ad68b5b134520218eedc59013c68519
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175929"
---
# <a name="imetadatadispenseropenscopeonmemory-method"></a><span data-ttu-id="11bde-102">IMetaDataDispenser::OpenScopeOnMemory メソッド</span><span class="sxs-lookup"><span data-stu-id="11bde-102">IMetaDataDispenser::OpenScopeOnMemory Method</span></span>
<span data-ttu-id="11bde-103">既存のメタデータを含むメモリ領域を開きます。</span><span class="sxs-lookup"><span data-stu-id="11bde-103">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="11bde-104">つまり、このメソッドは、既存のデータがメタデータとして扱われるメモリの指定された領域を開きます。</span><span class="sxs-lookup"><span data-stu-id="11bde-104">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11bde-105">構文</span><span class="sxs-lookup"><span data-stu-id="11bde-105">Syntax</span></span>  
  
```cpp  
HRESULT OpenScopeOnMemory (  
    [in]  LPCVOID     pData,
    [in]  ULONG       cbData,
    [in]  DWORD       dwOpenFlags,
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11bde-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="11bde-106">Parameters</span></span>  
 `pData`  
 <span data-ttu-id="11bde-107">[in]メモリ領域の開始アドレスを指定するポインター。</span><span class="sxs-lookup"><span data-stu-id="11bde-107">[in] A pointer that specifies the starting address of the memory area.</span></span>  
  
 `cbData`  
 <span data-ttu-id="11bde-108">[in]メモリ領域のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="11bde-108">[in] The size of the memory area, in bytes.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="11bde-109">[in]開くときのモード (読み取り、書き込みなど) を指定する[CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md)列挙体の値。</span><span class="sxs-lookup"><span data-stu-id="11bde-109">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="11bde-110">[in]返される必要なメタデータ インターフェイスの IID。呼び出し元は、インターフェイスを使用してメタデータをインポート (読み取り) または出力 (書き込み) します。</span><span class="sxs-lookup"><span data-stu-id="11bde-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="11bde-111">の値は`riid`、"インポート" または "出力" インターフェイスのいずれかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="11bde-111">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="11bde-112">有効な値は、IID_IMetaDataEmit、IID_IMetaDataImport、IID_IMetaDataAssemblyEmit、IID_IMetaDataAssemblyImport、IID_IMetaDataEmit2、またはIID_IMetaDataImport2です。</span><span class="sxs-lookup"><span data-stu-id="11bde-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="11bde-113">[アウト]返されたインターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="11bde-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11bde-114">解説</span><span class="sxs-lookup"><span data-stu-id="11bde-114">Remarks</span></span>  
 <span data-ttu-id="11bde-115">メタデータのインメモリ コピーは、"import" インターフェイスの 1 つからのメソッドを使用してクエリを実行したり、"emit" インターフェイスのメソッドを使用して追加したりできます。</span><span class="sxs-lookup"><span data-stu-id="11bde-115">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="11bde-116">この`OpenScopeOnMemory`メソッドは[IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)メソッドに似ていますが、対象のメタデータがディスク上のファイルではなくメモリに既に存在する点が異なります。</span><span class="sxs-lookup"><span data-stu-id="11bde-116">The `OpenScopeOnMemory` method is similar to the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method, except that the metadata of interest already exists in memory, rather than in a file on disk.</span></span>  
  
 <span data-ttu-id="11bde-117">メモリの対象領域に共通言語ランタイム (CLR) メタデータが含まれていない場合、`OpenScopeOnMemory`メソッドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="11bde-117">If the target area of memory does not contain common language runtime (CLR) metadata, the `OpenScopeOnMemory` method will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11bde-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="11bde-118">Requirements</span></span>  
 <span data-ttu-id="11bde-119">**プラットフォーム:**[「システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11bde-119">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11bde-120">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="11bde-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="11bde-121">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="11bde-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="11bde-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11bde-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11bde-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="11bde-123">See also</span></span>

- [<span data-ttu-id="11bde-124">IMetaDataDispenser インターフェイス</span><span class="sxs-lookup"><span data-stu-id="11bde-124">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="11bde-125">IMetaDataDispenserEx インターフェイス</span><span class="sxs-lookup"><span data-stu-id="11bde-125">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="11bde-126">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="11bde-126">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="11bde-127">IMetaDataAssemblyImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="11bde-127">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="11bde-128">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="11bde-128">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="11bde-129">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="11bde-129">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="11bde-130">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="11bde-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="11bde-131">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="11bde-131">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
