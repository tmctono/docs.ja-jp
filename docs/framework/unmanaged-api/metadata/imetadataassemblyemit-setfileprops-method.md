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
ms.openlocfilehash: 6505995b128e31ed2a18881d31afa0bb1bfe150e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779427"
---
# <a name="imetadataassemblyemitsetfileprops-method"></a><span data-ttu-id="acb63-102">IMetaDataAssemblyEmit::SetFileProps メソッド</span><span class="sxs-lookup"><span data-stu-id="acb63-102">IMetaDataAssemblyEmit::SetFileProps Method</span></span>
<span data-ttu-id="acb63-103">指定された `File` メタデータ構造体を変更します。</span><span class="sxs-lookup"><span data-stu-id="acb63-103">Modifies the specified `File` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acb63-104">構文</span><span class="sxs-lookup"><span data-stu-id="acb63-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,   
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="acb63-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="acb63-105">Parameters</span></span>  
 `file`  
 <span data-ttu-id="acb63-106">[in]メタデータ トークンを指定する、`File`メタデータ構造を変更します。</span><span class="sxs-lookup"><span data-stu-id="acb63-106">[in] The metadata token that specifies the `File` metadata structure to be modified.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="acb63-107">[in]ファイルに関連付けられているデータのハッシュへのポインター。</span><span class="sxs-lookup"><span data-stu-id="acb63-107">[in] A pointer to the hash data associated with the file.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="acb63-108">[in]バイト サイズ`pbHashValue`します。</span><span class="sxs-lookup"><span data-stu-id="acb63-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="acb63-109">[in]ビットごとの組み合わせ[CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md)ファイルのさまざまな属性を指定する値。</span><span class="sxs-lookup"><span data-stu-id="acb63-109">[in] A bitwise combination of [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values that specify various attributes of the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="acb63-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="acb63-110">Remarks</span></span>  
 <span data-ttu-id="acb63-111">作成する、`File`メタデータ構造体を使用して、 [imetadataassemblyemit::definefile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="acb63-111">To create a `File` metadata structure, use the [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acb63-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="acb63-112">Requirements</span></span>  
 <span data-ttu-id="acb63-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="acb63-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acb63-114">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="acb63-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="acb63-115">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="acb63-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="acb63-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acb63-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acb63-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="acb63-117">See also</span></span>

- [<span data-ttu-id="acb63-118">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="acb63-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
