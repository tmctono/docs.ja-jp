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
ms.openlocfilehash: ad2b3e5c452a5fc79e7a1cc0342cfc1d119a5fbd
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481990"
---
# <a name="imetadataemitdefinememberref-method"></a><span data-ttu-id="64bc4-102">IMetaDataEmit::DefineMemberRef メソッド</span><span class="sxs-lookup"><span data-stu-id="64bc4-102">IMetaDataEmit::DefineMemberRef Method</span></span>
<span data-ttu-id="64bc4-103">現在のスコープ外にあるモジュールのメンバーへの参照を定義し、その参照定義トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="64bc4-103">Defines a reference to a member of a module outside the current scope, and gets a token to that reference definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64bc4-104">構文</span><span class="sxs-lookup"><span data-stu-id="64bc4-104">Syntax</span></span>  
  
```  
HRESULT DefineMemberRef (   
    [in]  mdToken           tkImport,   
    [in]  LPCWSTR           szName,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [out] mdMemberRef       *pmr   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64bc4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="64bc4-105">Parameters</span></span>  
 `tkImport`  
 <span data-ttu-id="64bc4-106">[in]メンバーはグローバルです。 ない場合、ターゲット メンバーのクラスまたはインターフェイスのトークンメンバーが、グローバルな場合は、`mdModuleRef`その他のファイルのトークン。</span><span class="sxs-lookup"><span data-stu-id="64bc4-106">[in] Token for the target member's class or interface, if the member is not global; if the member is global, the `mdModuleRef` token for that other file.</span></span>  
  
 `szName`  
 <span data-ttu-id="64bc4-107">[in]対象メンバーの名前。</span><span class="sxs-lookup"><span data-stu-id="64bc4-107">[in] The name of the target member.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="64bc4-108">[in]対象メンバーのシグネチャ。</span><span class="sxs-lookup"><span data-stu-id="64bc4-108">[in] The signature of the target member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="64bc4-109">[in]内のバイト数`pvSigBlob`します。</span><span class="sxs-lookup"><span data-stu-id="64bc4-109">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="64bc4-110">[out]`mdMemberRef`に割り当てられたトークン。</span><span class="sxs-lookup"><span data-stu-id="64bc4-110">[out] The `mdMemberRef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64bc4-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="64bc4-111">Requirements</span></span>  
 <span data-ttu-id="64bc4-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="64bc4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64bc4-113">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="64bc4-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="64bc4-114">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="64bc4-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="64bc4-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64bc4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64bc4-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="64bc4-116">See also</span></span>
- [<span data-ttu-id="64bc4-117">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="64bc4-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="64bc4-118">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="64bc4-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
