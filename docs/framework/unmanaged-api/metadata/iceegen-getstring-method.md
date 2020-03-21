---
title: ICeeGen::GetString メソッド
ms.date: 03/30/2017
api_name:
- ICeeGen.GetString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetString
helpviewer_keywords:
- ICeeGen::GetString method [.NET Framework metadata]
- GetString method, ICeeGen interface [.NET Framework metadata]
ms.assetid: 7cc22562-128c-440a-9147-55ff20f173d7
topic_type:
- apiref
ms.openlocfilehash: ada126b41f1c634f7d8daa58480406ac26f92377
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177906"
---
# <a name="iceegengetstring-method"></a><span data-ttu-id="99866-102">ICeeGen::GetString メソッド</span><span class="sxs-lookup"><span data-stu-id="99866-102">ICeeGen::GetString Method</span></span>
<span data-ttu-id="99866-103">指定した相対仮想アドレスに格納されている文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="99866-103">Gets the string stored at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="99866-104">このメソッドは廃止され、使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="99866-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99866-105">構文</span><span class="sxs-lookup"><span data-stu-id="99866-105">Syntax</span></span>  
  
```cpp  
HRESULT GetString (  
    [in]  ULONG      RVA,
    [out] LPWSTR     *lpString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99866-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="99866-106">Parameters</span></span>  
 `RVA`  
 <span data-ttu-id="99866-107">[in]返される文字列の相対仮想アドレス。</span><span class="sxs-lookup"><span data-stu-id="99866-107">[in] The relative virtual address of the string to return.</span></span>  
  
 `lpString`  
 <span data-ttu-id="99866-108">[アウト]返された文字列。</span><span class="sxs-lookup"><span data-stu-id="99866-108">[out] The returned string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99866-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="99866-109">Requirements</span></span>  
 <span data-ttu-id="99866-110">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99866-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99866-111">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="99866-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="99866-112">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="99866-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="99866-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99866-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99866-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="99866-114">See also</span></span>

- [<span data-ttu-id="99866-115">ICeeGen インターフェイス</span><span class="sxs-lookup"><span data-stu-id="99866-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
