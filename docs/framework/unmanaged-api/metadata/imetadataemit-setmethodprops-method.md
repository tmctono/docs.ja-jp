---
title: IMetaDataEmit::SetMethodProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetMethodProps
helpviewer_keywords:
- SetMethodProps method [.NET Framework metadata]
- IMetaDataEmit::SetMethodProps method [.NET Framework metadata]
ms.assetid: e0c6ac12-22ea-43f5-b799-8cda0faf3336
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 534afdd5990435c6b4db5ef8ea27a8065b199496
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050013"
---
# <a name="imetadataemitsetmethodprops-method"></a><span data-ttu-id="13a83-102">IMetaDataEmit::SetMethodProps メソッド</span><span class="sxs-lookup"><span data-stu-id="13a83-102">IMetaDataEmit::SetMethodProps Method</span></span>
<span data-ttu-id="13a83-103">設定または更新、機能は、指定の相対仮想アドレス、前回の呼び出しによって定義されたメソッドに格納されている、 [imetadataemit::definemethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="13a83-103">Sets or updates the feature, stored at the specified relative virtual address, of a method defined by a prior call to [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13a83-104">構文</span><span class="sxs-lookup"><span data-stu-id="13a83-104">Syntax</span></span>  
  
```  
HRESULT SetMethodProps (   
    [in]  mdMethodDef md,   
    [in]  DWORD       dwMethodFlags,  
    [in]  ULONG       ulCodeRVA,   
    [in]  DWORD       dwImplFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13a83-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="13a83-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="13a83-106">[in]変更するメソッドのトークン。</span><span class="sxs-lookup"><span data-stu-id="13a83-106">[in] The token for the method to be changed.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="13a83-107">[in]メンバー属性。</span><span class="sxs-lookup"><span data-stu-id="13a83-107">[in] The member attributes.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="13a83-108">[in]コードのアドレス。</span><span class="sxs-lookup"><span data-stu-id="13a83-108">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="13a83-109">[in]メソッドの実装フラグ。</span><span class="sxs-lookup"><span data-stu-id="13a83-109">[in] The implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13a83-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="13a83-110">Requirements</span></span>  
 <span data-ttu-id="13a83-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="13a83-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13a83-112">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="13a83-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="13a83-113">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="13a83-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="13a83-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13a83-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13a83-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="13a83-115">See also</span></span>

- [<span data-ttu-id="13a83-116">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="13a83-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="13a83-117">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="13a83-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
