---
title: IMetaDataInfo::GetFileMapping メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataInfo.GetFileMapping
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataInfo::GetFileMapping
helpviewer_keywords:
- IMetaDataInfo::GetFileMapping method [.NET Framework metadata]
- GetFileMapping method [.NET Framework metadata]
ms.assetid: 2868dfec-c992-4606-88bb-a8e0b6b18271
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4c6a9473a698e4635c8b5cc9fb58963334dfd65e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59081792"
---
# <a name="imetadatainfogetfilemapping-method"></a><span data-ttu-id="c50cc-102">IMetaDataInfo::GetFileMapping メソッド</span><span class="sxs-lookup"><span data-stu-id="c50cc-102">IMetaDataInfo::GetFileMapping Method</span></span>
<span data-ttu-id="c50cc-103">マップのファイルとマッピングの種類のメモリ領域を取得します。</span><span class="sxs-lookup"><span data-stu-id="c50cc-103">Gets the memory region of the mapped file, and the type of mapping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c50cc-104">構文</span><span class="sxs-lookup"><span data-stu-id="c50cc-104">Syntax</span></span>  
  
```  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,   
    [out] ULONGLONG            *pcbData,   
    [out] DWORD                *pdwMappingType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c50cc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c50cc-105">Parameters</span></span>  
 `ppvData`  
 <span data-ttu-id="c50cc-106">[out]マップされたファイルの先頭へのポインター。</span><span class="sxs-lookup"><span data-stu-id="c50cc-106">[out] A pointer to the start of the mapped file.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="c50cc-107">[out]マップ領域のサイズ。</span><span class="sxs-lookup"><span data-stu-id="c50cc-107">[out] The size of the mapped region.</span></span> <span data-ttu-id="c50cc-108">場合`pdwMappingType`は`fmFlat`、これは、ファイルのサイズです。</span><span class="sxs-lookup"><span data-stu-id="c50cc-108">If `pdwMappingType` is `fmFlat`, this is the size of the file.</span></span>  
  
 `pdwMappingType`  
 <span data-ttu-id="c50cc-109">[out]A [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)マッピングの種類を示す値。</span><span class="sxs-lookup"><span data-stu-id="c50cc-109">[out] A [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) value that indicates the type of mapping.</span></span> <span data-ttu-id="c50cc-110">現在の実装の共通言語ランタイム (CLR) 常に返します`fmFlat`します。</span><span class="sxs-lookup"><span data-stu-id="c50cc-110">The current implementation of the common language runtime (CLR) always returns `fmFlat`.</span></span> <span data-ttu-id="c50cc-111">その他の値は、将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="c50cc-111">Other values are reserved for future use.</span></span> <span data-ttu-id="c50cc-112">ただし、将来のバージョンで有効にすることがありますまたはサービス リリースで他の値であるために、常に、戻り値を確認してください。</span><span class="sxs-lookup"><span data-stu-id="c50cc-112">However, you should always verify the returned value, because other values may be enabled in future versions or service releases.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c50cc-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="c50cc-113">Return Value</span></span>  
  
|<span data-ttu-id="c50cc-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c50cc-114">HRESULT</span></span>|<span data-ttu-id="c50cc-115">説明</span><span class="sxs-lookup"><span data-stu-id="c50cc-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="c50cc-116">すべての出力が入力されます。</span><span class="sxs-lookup"><span data-stu-id="c50cc-116">All outputs are filled.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="c50cc-117">引数の値として NULL が渡されました。</span><span class="sxs-lookup"><span data-stu-id="c50cc-117">NULL was passed as an argument value.</span></span>|  
|`COR_E_NOTSUPPORTED`|<span data-ttu-id="c50cc-118">CLR の実装では、メモリ領域に関する情報を提供できません。</span><span class="sxs-lookup"><span data-stu-id="c50cc-118">The CLR implementation cannot provide information about the memory region.</span></span> <span data-ttu-id="c50cc-119">これは、次の理由で発生します。</span><span class="sxs-lookup"><span data-stu-id="c50cc-119">This can happen for the following reasons:</span></span><br /><br /> <span data-ttu-id="c50cc-120">メタデータ スコープが開かれた、`ofWrite`または`ofCopyMemory`フラグ。</span><span class="sxs-lookup"><span data-stu-id="c50cc-120">-   The metadata scope was opened with the `ofWrite` or `ofCopyMemory` flag.</span></span><br /><span data-ttu-id="c50cc-121">-なしのメタデータ スコープが開かれた、`ofReadOnly`フラグ。</span><span class="sxs-lookup"><span data-stu-id="c50cc-121">-   The metadata scope was opened without the `ofReadOnly` flag.</span></span><br /><span data-ttu-id="c50cc-122">- [Imetadatadispenser::openscopeonmemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md)メソッドがファイルのメタデータ部分のみを開くために使用されました。</span><span class="sxs-lookup"><span data-stu-id="c50cc-122">-   The [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) method was used to open only the metadata portion of the file.</span></span><br /><span data-ttu-id="c50cc-123">-ファイルは、ポータブル実行可能 (PE) ファイルではありません。</span><span class="sxs-lookup"><span data-stu-id="c50cc-123">-   The file is not a portable executable (PE) file.</span></span> <span data-ttu-id="c50cc-124">**注:** これらの条件は、CLR の実装に依存しが将来のバージョンの CLR が緩和される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c50cc-124">**Note:**  These conditions depend on the CLR implementation, and are likely to be weakened in future versions of the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c50cc-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="c50cc-125">Remarks</span></span>  
 <span data-ttu-id="c50cc-126">メモリを`ppvData`のみと基になるメタデータ スコープが開いている限りへのポインターが有効です。</span><span class="sxs-lookup"><span data-stu-id="c50cc-126">The memory that `ppvData` points to is valid only as long as the underlying metadata scope is open.</span></span>  
  
 <span data-ttu-id="c50cc-127">このメソッドを呼び出すことによってメモリにディスク上のファイルのメタデータをマップするときに、機能するために、 [imetadatadispenser::openscope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)メソッドを指定する必要がある、`ofReadOnly`とフラグを指定する必要があります、`ofWrite`または`ofCopyMemory`フラグ。</span><span class="sxs-lookup"><span data-stu-id="c50cc-127">In order for this method to work, when you map the metadata of an on-disk file into memory by calling the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method, you must specify the `ofReadOnly` flag and you must not specify the `ofWrite` or `ofCopyMemory` flag.</span></span>  
  
 <span data-ttu-id="c50cc-128">各スコープのファイル マッピングの種類の選択は、CLR の特定の実装に固有です。</span><span class="sxs-lookup"><span data-stu-id="c50cc-128">The choice of file mapping type for each scope is specific to a given implementation of the CLR.</span></span> <span data-ttu-id="c50cc-129">ユーザーによって設定ことはできません。</span><span class="sxs-lookup"><span data-stu-id="c50cc-129">It cannot be set by the user.</span></span> <span data-ttu-id="c50cc-130">常に、CLR の現在実装`fmFlat`で`pdwMappingType`がこれを変更できますで将来のバージョンの CLR または将来の指定したバージョンのサービス リリースです。</span><span class="sxs-lookup"><span data-stu-id="c50cc-130">The current implementation of the CLR always returns `fmFlat` in `pdwMappingType`, but this can change in future versions of the CLR or in future service releases of a given version.</span></span> <span data-ttu-id="c50cc-131">返される値を常に確認する必要があります`pdwMappingType`さまざまな種類がさまざまなレイアウトやオフセットを持つため、します。</span><span class="sxs-lookup"><span data-stu-id="c50cc-131">You should always check the returned value in `pdwMappingType`, because different types will have different layouts and offsets.</span></span>  
  
 <span data-ttu-id="c50cc-132">3 つのパラメーターのいずれかの NULL を渡すことはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c50cc-132">Passing NULL for any of the three parameters is not supported.</span></span> <span data-ttu-id="c50cc-133">メソッドを返します`E_INVALIDARG`出力のいずれもがいっぱいになるとします。</span><span class="sxs-lookup"><span data-stu-id="c50cc-133">The method returns `E_INVALIDARG`, and none of the outputs are filled.</span></span> <span data-ttu-id="c50cc-134">マッピングの種類や領域のサイズを無視すると、プログラムが異常終了があります。</span><span class="sxs-lookup"><span data-stu-id="c50cc-134">Ignoring the mapping type or the size of the region can result in abnormal program termination.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c50cc-135">必要条件</span><span class="sxs-lookup"><span data-stu-id="c50cc-135">Requirements</span></span>  
 <span data-ttu-id="c50cc-136">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c50cc-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c50cc-137">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c50cc-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c50cc-138">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="c50cc-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="c50cc-139">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="c50cc-139">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c50cc-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="c50cc-140">See also</span></span>

- [<span data-ttu-id="c50cc-141">IMetaDataInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c50cc-141">IMetaDataInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)
- [<span data-ttu-id="c50cc-142">CorFileMapping 列挙体</span><span class="sxs-lookup"><span data-stu-id="c50cc-142">CorFileMapping Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)
