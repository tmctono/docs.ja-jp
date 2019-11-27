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
ms.openlocfilehash: 0cd2071d4410615a08e774ba30e0e8fe8d1fa7c7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436178"
---
# <a name="imetadatainfogetfilemapping-method"></a><span data-ttu-id="a03fe-102">IMetaDataInfo::GetFileMapping メソッド</span><span class="sxs-lookup"><span data-stu-id="a03fe-102">IMetaDataInfo::GetFileMapping Method</span></span>
<span data-ttu-id="a03fe-103">マップされたファイルのメモリ領域とマッピングの種類を取得します。</span><span class="sxs-lookup"><span data-stu-id="a03fe-103">Gets the memory region of the mapped file, and the type of mapping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a03fe-104">構文</span><span class="sxs-lookup"><span data-stu-id="a03fe-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,   
    [out] ULONGLONG            *pcbData,   
    [out] DWORD                *pdwMappingType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a03fe-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a03fe-105">Parameters</span></span>  
 `ppvData`  
 <span data-ttu-id="a03fe-106">入出力マップされたファイルの先頭へのポインター。</span><span class="sxs-lookup"><span data-stu-id="a03fe-106">[out] A pointer to the start of the mapped file.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="a03fe-107">入出力マップされた領域のサイズ。</span><span class="sxs-lookup"><span data-stu-id="a03fe-107">[out] The size of the mapped region.</span></span> <span data-ttu-id="a03fe-108">`pdwMappingType` が `fmFlat`場合は、ファイルのサイズです。</span><span class="sxs-lookup"><span data-stu-id="a03fe-108">If `pdwMappingType` is `fmFlat`, this is the size of the file.</span></span>  
  
 `pdwMappingType`  
 <span data-ttu-id="a03fe-109">入出力マッピングの種類を示す[CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)値です。</span><span class="sxs-lookup"><span data-stu-id="a03fe-109">[out] A [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) value that indicates the type of mapping.</span></span> <span data-ttu-id="a03fe-110">共通言語ランタイム (CLR) の現在の実装では、常に `fmFlat`を返します。</span><span class="sxs-lookup"><span data-stu-id="a03fe-110">The current implementation of the common language runtime (CLR) always returns `fmFlat`.</span></span> <span data-ttu-id="a03fe-111">他の値は将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="a03fe-111">Other values are reserved for future use.</span></span> <span data-ttu-id="a03fe-112">ただし、その他の値は将来のバージョンまたはサービスリリースで有効になる可能性があるため、常に戻り値を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a03fe-112">However, you should always verify the returned value, because other values may be enabled in future versions or service releases.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a03fe-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="a03fe-113">Return Value</span></span>  
  
|<span data-ttu-id="a03fe-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a03fe-114">HRESULT</span></span>|<span data-ttu-id="a03fe-115">説明</span><span class="sxs-lookup"><span data-stu-id="a03fe-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a03fe-116">すべての出力が入力されます。</span><span class="sxs-lookup"><span data-stu-id="a03fe-116">All outputs are filled.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="a03fe-117">引数の値として NULL が渡されました。</span><span class="sxs-lookup"><span data-stu-id="a03fe-117">NULL was passed as an argument value.</span></span>|  
|`COR_E_NOTSUPPORTED`|<span data-ttu-id="a03fe-118">CLR 実装では、メモリ領域に関する情報を提供できません。</span><span class="sxs-lookup"><span data-stu-id="a03fe-118">The CLR implementation cannot provide information about the memory region.</span></span> <span data-ttu-id="a03fe-119">これは、次の理由で発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="a03fe-119">This can happen for the following reasons:</span></span><br /><br /> <span data-ttu-id="a03fe-120">-メタデータスコープが、`ofWrite` または `ofCopyMemory` フラグで開かれました。</span><span class="sxs-lookup"><span data-stu-id="a03fe-120">-   The metadata scope was opened with the `ofWrite` or `ofCopyMemory` flag.</span></span><br /><span data-ttu-id="a03fe-121">-`ofReadOnly` フラグを指定せずにメタデータスコープが開かれました。</span><span class="sxs-lookup"><span data-stu-id="a03fe-121">-   The metadata scope was opened without the `ofReadOnly` flag.</span></span><br /><span data-ttu-id="a03fe-122">- [IMetaDataDispenser:: OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md)メソッドは、ファイルのメタデータ部分のみを開くために使用されました。</span><span class="sxs-lookup"><span data-stu-id="a03fe-122">-   The [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) method was used to open only the metadata portion of the file.</span></span><br /><span data-ttu-id="a03fe-123">-ファイルは、ポータブル実行可能 (PE) ファイルではありません。</span><span class="sxs-lookup"><span data-stu-id="a03fe-123">-   The file is not a portable executable (PE) file.</span></span> <span data-ttu-id="a03fe-124">**注:** これらの条件は CLR の実装によって異なり、CLR の将来のバージョンでは緩和される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a03fe-124">**Note:**  These conditions depend on the CLR implementation, and are likely to be weakened in future versions of the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a03fe-125">コメント</span><span class="sxs-lookup"><span data-stu-id="a03fe-125">Remarks</span></span>  
 <span data-ttu-id="a03fe-126">`ppvData` が指すメモリは、基になるメタデータスコープが開いている間のみ有効です。</span><span class="sxs-lookup"><span data-stu-id="a03fe-126">The memory that `ppvData` points to is valid only as long as the underlying metadata scope is open.</span></span>  
  
 <span data-ttu-id="a03fe-127">このメソッドを機能させるには、 [IMetaDataDispenser:: OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)メソッドを呼び出して、ディスク上のファイルのメタデータをメモリにマップするときに、`ofReadOnly` フラグを指定し、`ofWrite` または `ofCopyMemory` フラグを指定しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a03fe-127">In order for this method to work, when you map the metadata of an on-disk file into memory by calling the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method, you must specify the `ofReadOnly` flag and you must not specify the `ofWrite` or `ofCopyMemory` flag.</span></span>  
  
 <span data-ttu-id="a03fe-128">各スコープでのファイルマッピングの種類の選択は、CLR の特定の実装に固有です。</span><span class="sxs-lookup"><span data-stu-id="a03fe-128">The choice of file mapping type for each scope is specific to a given implementation of the CLR.</span></span> <span data-ttu-id="a03fe-129">ユーザーが設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="a03fe-129">It cannot be set by the user.</span></span> <span data-ttu-id="a03fe-130">CLR の現在の実装では、常に `pdwMappingType`で `fmFlat` が返されますが、これは CLR の将来のバージョンまたは特定のバージョンの今後のサービスリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a03fe-130">The current implementation of the CLR always returns `fmFlat` in `pdwMappingType`, but this can change in future versions of the CLR or in future service releases of a given version.</span></span> <span data-ttu-id="a03fe-131">型によってレイアウトとオフセットが異なるため、必ず `pdwMappingType`で戻り値を確認してください。</span><span class="sxs-lookup"><span data-stu-id="a03fe-131">You should always check the returned value in `pdwMappingType`, because different types will have different layouts and offsets.</span></span>  
  
 <span data-ttu-id="a03fe-132">3つのパラメーターのいずれかに対して NULL を渡すことはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a03fe-132">Passing NULL for any of the three parameters is not supported.</span></span> <span data-ttu-id="a03fe-133">メソッドは `E_INVALIDARG`を返し、出力はすべて入力されません。</span><span class="sxs-lookup"><span data-stu-id="a03fe-133">The method returns `E_INVALIDARG`, and none of the outputs are filled.</span></span> <span data-ttu-id="a03fe-134">マッピングの種類または領域のサイズを無視すると、プログラムが異常終了する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a03fe-134">Ignoring the mapping type or the size of the region can result in abnormal program termination.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a03fe-135">要件</span><span class="sxs-lookup"><span data-stu-id="a03fe-135">Requirements</span></span>  
 <span data-ttu-id="a03fe-136">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a03fe-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a03fe-137">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="a03fe-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a03fe-138">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="a03fe-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a03fe-139">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a03fe-139">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a03fe-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="a03fe-140">See also</span></span>

- [<span data-ttu-id="a03fe-141">IMetaDataInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a03fe-141">IMetaDataInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)
- [<span data-ttu-id="a03fe-142">CorFileMapping 列挙型</span><span class="sxs-lookup"><span data-stu-id="a03fe-142">CorFileMapping Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)
