---
title: IMetaDataAssemblyEmit::SetFileProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetFileProps
helpviewer_keywords:
- IMetaDataAssemblyEmit::SetFileProps method [.NET Framework metadata]
- SetFileProps method [.NET Framework metadata]
ms.assetid: 85667d38-611c-45a9-938d-930ac7a7b681
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fd0c2da234fa89bbf92c2117d6428d64502da0c5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59208177"
---
# <a name="imetadataassemblyemitsetfileprops-method"></a><span data-ttu-id="53cd7-102">IMetaDataAssemblyEmit::SetFileProps メソッド</span><span class="sxs-lookup"><span data-stu-id="53cd7-102">IMetaDataAssemblyEmit::SetFileProps Method</span></span>
<span data-ttu-id="53cd7-103">指定された `File` メタデータ構造体を変更します。</span><span class="sxs-lookup"><span data-stu-id="53cd7-103">Modifies the specified `File` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53cd7-104">構文</span><span class="sxs-lookup"><span data-stu-id="53cd7-104">Syntax</span></span>  
  
```  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,   
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53cd7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="53cd7-105">Parameters</span></span>  
 `file`  
 <span data-ttu-id="53cd7-106">[in]メタデータ トークンを指定する、`File`メタデータ構造を変更します。</span><span class="sxs-lookup"><span data-stu-id="53cd7-106">[in] The metadata token that specifies the `File` metadata structure to be modified.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="53cd7-107">[in]ファイルに関連付けられているデータのハッシュへのポインター。</span><span class="sxs-lookup"><span data-stu-id="53cd7-107">[in] A pointer to the hash data associated with the file.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="53cd7-108">[in]バイト サイズ`pbHashValue`します。</span><span class="sxs-lookup"><span data-stu-id="53cd7-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="53cd7-109">[in]ビットごとの組み合わせ[CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md)ファイルのさまざまな属性を指定する値。</span><span class="sxs-lookup"><span data-stu-id="53cd7-109">[in] A bitwise combination of [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values that specify various attributes of the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="53cd7-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="53cd7-110">Remarks</span></span>  
 <span data-ttu-id="53cd7-111">作成する、`File`メタデータ構造体を使用して、 [imetadataassemblyemit::definefile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="53cd7-111">To create a `File` metadata structure, use the [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53cd7-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="53cd7-112">Requirements</span></span>  
 <span data-ttu-id="53cd7-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="53cd7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53cd7-114">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="53cd7-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="53cd7-115">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="53cd7-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="53cd7-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53cd7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53cd7-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="53cd7-117">See also</span></span>

- [<span data-ttu-id="53cd7-118">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="53cd7-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
