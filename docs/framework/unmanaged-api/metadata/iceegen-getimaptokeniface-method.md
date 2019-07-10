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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b42c7ed5614f5f436559ce4af462ff16896a89c0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746141"
---
# <a name="iceegengetimaptokeniface-method"></a><span data-ttu-id="72536-102">ICeeGen::GetIMapTokenIface メソッド</span><span class="sxs-lookup"><span data-stu-id="72536-102">ICeeGen::GetIMapTokenIface Method</span></span>
<span data-ttu-id="72536-103">指定したトークンによって参照されているインターフェイスを取得します。</span><span class="sxs-lookup"><span data-stu-id="72536-103">Gets the interface referenced by the specified token.</span></span>  
  
 <span data-ttu-id="72536-104">このメソッドは廃止され、使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="72536-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72536-105">構文</span><span class="sxs-lookup"><span data-stu-id="72536-105">Syntax</span></span>  
  
```cpp  
HRESULT GetIMapTokenIface (  
    [in, out] IUnknown   **pIMapToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72536-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="72536-106">Parameters</span></span>  
 `pIMapToken`  
 <span data-ttu-id="72536-107">[入力、出力]返されるインターフェイスのメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="72536-107">[in, out] The metadata token for the interface to be returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72536-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="72536-108">Requirements</span></span>  
 <span data-ttu-id="72536-109">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="72536-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72536-110">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="72536-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="72536-111">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="72536-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="72536-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72536-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72536-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="72536-113">See also</span></span>

- [<span data-ttu-id="72536-114">ICeeGen インターフェイス</span><span class="sxs-lookup"><span data-stu-id="72536-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
