---
title: IMetaDataEmit::DefineMemberRef メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMemberRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMemberRef
helpviewer_keywords:
- DefineMemberRef method [.NET Framework metadata]
- IMetaDataEmit::DefineMemberRef method [.NET Framework metadata]
ms.assetid: 21b5bcb8-ea75-4962-8acc-ad17584061e5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 38e4928ad0f3560698cbecab81a11630d67e4db2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777615"
---
# <a name="imetadataemitdefinememberref-method"></a><span data-ttu-id="58754-102">IMetaDataEmit::DefineMemberRef メソッド</span><span class="sxs-lookup"><span data-stu-id="58754-102">IMetaDataEmit::DefineMemberRef Method</span></span>
<span data-ttu-id="58754-103">現在のスコープ外にあるモジュールのメンバーへの参照を定義し、その参照定義トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="58754-103">Defines a reference to a member of a module outside the current scope, and gets a token to that reference definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58754-104">構文</span><span class="sxs-lookup"><span data-stu-id="58754-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMemberRef (   
    [in]  mdToken           tkImport,   
    [in]  LPCWSTR           szName,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [out] mdMemberRef       *pmr   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58754-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="58754-105">Parameters</span></span>  
 `tkImport`  
 <span data-ttu-id="58754-106">[in]メンバーはグローバルです。 ない場合、ターゲット メンバーのクラスまたはインターフェイスのトークンメンバーが、グローバルな場合は、`mdModuleRef`その他のファイルのトークン。</span><span class="sxs-lookup"><span data-stu-id="58754-106">[in] Token for the target member's class or interface, if the member is not global; if the member is global, the `mdModuleRef` token for that other file.</span></span>  
  
 `szName`  
 <span data-ttu-id="58754-107">[in]対象メンバーの名前。</span><span class="sxs-lookup"><span data-stu-id="58754-107">[in] The name of the target member.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="58754-108">[in]対象メンバーのシグネチャ。</span><span class="sxs-lookup"><span data-stu-id="58754-108">[in] The signature of the target member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="58754-109">[in]内のバイト数`pvSigBlob`します。</span><span class="sxs-lookup"><span data-stu-id="58754-109">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="58754-110">[out]`mdMemberRef`に割り当てられたトークン。</span><span class="sxs-lookup"><span data-stu-id="58754-110">[out] The `mdMemberRef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58754-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="58754-111">Requirements</span></span>  
 <span data-ttu-id="58754-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="58754-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58754-113">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="58754-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="58754-114">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="58754-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="58754-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58754-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58754-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="58754-116">See also</span></span>

- [<span data-ttu-id="58754-117">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="58754-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="58754-118">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="58754-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
