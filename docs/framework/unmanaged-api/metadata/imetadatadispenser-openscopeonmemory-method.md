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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 732ec6cbb2158037252bc2ea4bf406f47f11da9f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050195"
---
# <a name="imetadatadispenseropenscopeonmemory-method"></a><span data-ttu-id="6a7c8-102">IMetaDataDispenser::OpenScopeOnMemory メソッド</span><span class="sxs-lookup"><span data-stu-id="6a7c8-102">IMetaDataDispenser::OpenScopeOnMemory Method</span></span>
<span data-ttu-id="6a7c8-103">既存のメタデータを含むメモリの領域を開きます。</span><span class="sxs-lookup"><span data-stu-id="6a7c8-103">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="6a7c8-104">つまり、このメソッドは、既存のデータはメタデータとして扱われますメモリの指定された領域を開きます。</span><span class="sxs-lookup"><span data-stu-id="6a7c8-104">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a7c8-105">構文</span><span class="sxs-lookup"><span data-stu-id="6a7c8-105">Syntax</span></span>  
  
```  
HRESULT OpenScopeOnMemory (  
    [in]  LPCVOID     pData,   
    [in]  ULONG       cbData,   
    [in]  DWORD       dwOpenFlags,   
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a7c8-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6a7c8-106">Parameters</span></span>  
 `pData`  
 <span data-ttu-id="6a7c8-107">[in]メモリ領域の開始アドレスを指定するポインター。</span><span class="sxs-lookup"><span data-stu-id="6a7c8-107">[in] A pointer that specifies the starting address of the memory area.</span></span>  
  
 `cbData`  
 <span data-ttu-id="6a7c8-108">[in]\(バイト単位) のメモリ領域のサイズ。</span><span class="sxs-lookup"><span data-stu-id="6a7c8-108">[in] The size of the memory area, in bytes.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="6a7c8-109">[in]値、 [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md)開くのためのモード (読み取り、書き込み、およびなど) を指定する列挙体。</span><span class="sxs-lookup"><span data-stu-id="6a7c8-109">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="6a7c8-110">[in]返される必要なメタデータ インターフェイスの IID呼び出し元は (読み取り) をインポートまたは (書き込み) メタデータを生成するインターフェイスを使用します。</span><span class="sxs-lookup"><span data-stu-id="6a7c8-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="6a7c8-111">値`riid`"import"や「生成」インターフェイスのいずれかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a7c8-111">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="6a7c8-112">有効な値は、IID_IMetaDataEmit、IID_IMetaDataImport、IID_IMetaDataAssemblyEmit、IID_IMetaDataAssemblyImport、IID_IMetaDataEmit2、または IID_IMetaDataImport2 は。</span><span class="sxs-lookup"><span data-stu-id="6a7c8-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="6a7c8-113">[out]返されたインターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="6a7c8-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6a7c8-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="6a7c8-114">Remarks</span></span>  
 <span data-ttu-id="6a7c8-115">メソッドを使用して、"import"インターフェイスのいずれかからまたは「生成」インターフェイスのいずれかからメソッドを使用する追加メタデータのメモリ内コピーを照会できます。</span><span class="sxs-lookup"><span data-stu-id="6a7c8-115">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="6a7c8-116">`OpenScopeOnMemory`メソッドは、 [imetadatadispenser::openscope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)メソッド、関心のあるメタデータは、ディスク上のファイルではなく、メモリ内に既に存在している点が異なります。</span><span class="sxs-lookup"><span data-stu-id="6a7c8-116">The `OpenScopeOnMemory` method is similar to the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method, except that the metadata of interest already exists in memory, rather than in a file on disk.</span></span>  
  
 <span data-ttu-id="6a7c8-117">メモリのターゲットの領域に共通言語ランタイム (CLR) メタデータが含まれていない場合、`OpenScopeOnMemory`メソッドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="6a7c8-117">If the target area of memory does not contain common language runtime (CLR) metadata, the `OpenScopeOnMemory` method will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a7c8-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="6a7c8-118">Requirements</span></span>  
 <span data-ttu-id="6a7c8-119">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a7c8-119">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a7c8-120">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6a7c8-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6a7c8-121">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="6a7c8-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6a7c8-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a7c8-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a7c8-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="6a7c8-123">See also</span></span>

- [<span data-ttu-id="6a7c8-124">IMetaDataDispenser インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6a7c8-124">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="6a7c8-125">IMetaDataDispenserEx インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6a7c8-125">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="6a7c8-126">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6a7c8-126">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="6a7c8-127">IMetaDataAssemblyImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6a7c8-127">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="6a7c8-128">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6a7c8-128">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="6a7c8-129">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6a7c8-129">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="6a7c8-130">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6a7c8-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="6a7c8-131">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6a7c8-131">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
