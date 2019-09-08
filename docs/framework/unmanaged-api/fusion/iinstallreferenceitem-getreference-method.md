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
ms.openlocfilehash: 9395fcc6d896114c25770edbc17761323285099f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796399"
---
# <a name="iinstallreferenceitemgetreference-method"></a><span data-ttu-id="f9eae-102">IInstallReferenceItem::GetReference メソッド</span><span class="sxs-lookup"><span data-stu-id="f9eae-102">IInstallReferenceItem::GetReference Method</span></span>
<span data-ttu-id="f9eae-103">この[Iinstallreferenceitem](iinstallreferenceitem-interface.md)オブジェクトによって表される[FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md)構造体へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="f9eae-103">Gets a pointer to the [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) structure represented by this [IInstallReferenceItem](iinstallreferenceitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9eae-104">構文</span><span class="sxs-lookup"><span data-stu-id="f9eae-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReference (  
    [out] LPFUSION_INSTALL_REFERENCE *ppRefData,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9eae-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f9eae-105">Parameters</span></span>  
 `ppRefData`  
 <span data-ttu-id="f9eae-106">入出力返され`FUSION_INSTALL_REFERENCE`たポインター。</span><span class="sxs-lookup"><span data-stu-id="f9eae-106">[out] The returned `FUSION_INSTALL_REFERENCE` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="f9eae-107">[入力] 将来の機能拡張に備えて予約されています。</span><span class="sxs-lookup"><span data-stu-id="f9eae-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="f9eae-108">`dwFlags`0 (ゼロ) にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9eae-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="f9eae-109">[入力] 将来の機能拡張に備えて予約されています。</span><span class="sxs-lookup"><span data-stu-id="f9eae-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="f9eae-110">`pvReserved`null 参照である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9eae-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9eae-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="f9eae-111">Requirements</span></span>  
 <span data-ttu-id="f9eae-112">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9eae-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9eae-113">**ヘッダー:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="f9eae-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="f9eae-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9eae-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9eae-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="f9eae-115">See also</span></span>

- [<span data-ttu-id="f9eae-116">IInstallReferenceItem インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f9eae-116">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
- [<span data-ttu-id="f9eae-117">FUSION_INSTALL_REFERENCE 構造体</span><span class="sxs-lookup"><span data-stu-id="f9eae-117">FUSION_INSTALL_REFERENCE Structure</span></span>](fusion-install-reference-structure.md)
