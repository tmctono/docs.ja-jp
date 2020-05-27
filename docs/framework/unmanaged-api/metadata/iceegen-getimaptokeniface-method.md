---
title: ICeeGen::GetIMapTokenIface メソッド
ms.date: 03/30/2017
api_name:
- ICeeGen.GetIMapTokenIface
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetIMapTokenIface
helpviewer_keywords:
- GetIMapTokenIface method [.NET Framework metadata]
- ICeeGen::GetIMapTokenIface method [.NET Framework metadata]
ms.assetid: 847a5531-c37d-49cd-8844-9e54b5d86cf7
topic_type:
- apiref
ms.openlocfilehash: 074279a0f5757b0d8ee96aa7075f9422be8da0c1
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008353"
---
# <a name="iceegengetimaptokeniface-method"></a><span data-ttu-id="2bda1-102">ICeeGen::GetIMapTokenIface メソッド</span><span class="sxs-lookup"><span data-stu-id="2bda1-102">ICeeGen::GetIMapTokenIface Method</span></span>
<span data-ttu-id="2bda1-103">指定したトークンによって参照されるインターフェイスを取得します。</span><span class="sxs-lookup"><span data-stu-id="2bda1-103">Gets the interface referenced by the specified token.</span></span>  
  
 <span data-ttu-id="2bda1-104">このメソッドは互換性のために残されています。使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="2bda1-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bda1-105">構文</span><span class="sxs-lookup"><span data-stu-id="2bda1-105">Syntax</span></span>  
  
```cpp  
HRESULT GetIMapTokenIface (  
    [in, out] IUnknown   **pIMapToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bda1-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2bda1-106">Parameters</span></span>  
 `pIMapToken`  
 <span data-ttu-id="2bda1-107">[入力、出力]返されるインターフェイスのメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="2bda1-107">[in, out] The metadata token for the interface to be returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bda1-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="2bda1-108">Requirements</span></span>  
 <span data-ttu-id="2bda1-109">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2bda1-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bda1-110">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="2bda1-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2bda1-111">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="2bda1-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2bda1-112">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bda1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bda1-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="2bda1-113">See also</span></span>

- [<span data-ttu-id="2bda1-114">ICeeGen インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2bda1-114">ICeeGen Interface</span></span>](iceegen-interface.md)
