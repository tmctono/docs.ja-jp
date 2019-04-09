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
ms.openlocfilehash: dc6581fc21b975ff5f50db62a571881606765c54
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076602"
---
# <a name="iceegengetimaptokeniface-method"></a><span data-ttu-id="6c796-102">ICeeGen::GetIMapTokenIface メソッド</span><span class="sxs-lookup"><span data-stu-id="6c796-102">ICeeGen::GetIMapTokenIface Method</span></span>
<span data-ttu-id="6c796-103">指定したトークンによって参照されているインターフェイスを取得します。</span><span class="sxs-lookup"><span data-stu-id="6c796-103">Gets the interface referenced by the specified token.</span></span>  
  
 <span data-ttu-id="6c796-104">このメソッドは廃止され、使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c796-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c796-105">構文</span><span class="sxs-lookup"><span data-stu-id="6c796-105">Syntax</span></span>  
  
```  
HRESULT GetIMapTokenIface (  
    [in, out] IUnknown   **pIMapToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c796-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6c796-106">Parameters</span></span>  
 `pIMapToken`  
 <span data-ttu-id="6c796-107">[入力、出力]返されるインターフェイスのメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="6c796-107">[in, out] The metadata token for the interface to be returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c796-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="6c796-108">Requirements</span></span>  
 <span data-ttu-id="6c796-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c796-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c796-110">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6c796-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6c796-111">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="6c796-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="6c796-112">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="6c796-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6c796-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="6c796-113">See also</span></span>

- [<span data-ttu-id="6c796-114">ICeeGen インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6c796-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
