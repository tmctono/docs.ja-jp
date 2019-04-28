---
title: IInstallReferenceItem::GetReference メソッド
ms.date: 03/30/2017
api_name:
- IInstallReferenceItem.GetReference
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceItem::GetReference
helpviewer_keywords:
- IInstallReferenceItem::GetReference method [.NET Framework fusion]
- GetReference method [.NET Framework fusion]
ms.assetid: 8960332f-c98a-405a-ba92-7003de0c1187
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd0a554535122b81f5812102c7951f56b294796a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757678"
---
# <a name="iinstallreferenceitemgetreference-method"></a><span data-ttu-id="09ac9-102">IInstallReferenceItem::GetReference メソッド</span><span class="sxs-lookup"><span data-stu-id="09ac9-102">IInstallReferenceItem::GetReference Method</span></span>
<span data-ttu-id="09ac9-103">ポインターを取得、 [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md)構造体によって表される[IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="09ac9-103">Gets a pointer to the [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) structure represented by this [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09ac9-104">構文</span><span class="sxs-lookup"><span data-stu-id="09ac9-104">Syntax</span></span>  
  
```  
HRESULT GetReference (  
    [out] LPFUSION_INSTALL_REFERENCE *ppRefData,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09ac9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="09ac9-105">Parameters</span></span>  
 `ppRefData`  
 <span data-ttu-id="09ac9-106">[out]返された`FUSION_INSTALL_REFERENCE`ポインター。</span><span class="sxs-lookup"><span data-stu-id="09ac9-106">[out] The returned `FUSION_INSTALL_REFERENCE` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="09ac9-107">[入力] 将来の機能拡張に備えて予約されています。</span><span class="sxs-lookup"><span data-stu-id="09ac9-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="09ac9-108">`dwFlags` 0 (ゼロ) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="09ac9-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="09ac9-109">[入力] 将来の機能拡張に備えて予約されています。</span><span class="sxs-lookup"><span data-stu-id="09ac9-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="09ac9-110">`pvReserved` null 参照である必要があります。</span><span class="sxs-lookup"><span data-stu-id="09ac9-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09ac9-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="09ac9-111">Requirements</span></span>  
 <span data-ttu-id="09ac9-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="09ac9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09ac9-113">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="09ac9-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="09ac9-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09ac9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09ac9-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="09ac9-115">See also</span></span>

- [<span data-ttu-id="09ac9-116">IInstallReferenceItem インターフェイス</span><span class="sxs-lookup"><span data-stu-id="09ac9-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)
- [<span data-ttu-id="09ac9-117">FUSION_INSTALL_REFERENCE 構造体</span><span class="sxs-lookup"><span data-stu-id="09ac9-117">FUSION_INSTALL_REFERENCE Structure</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md)
