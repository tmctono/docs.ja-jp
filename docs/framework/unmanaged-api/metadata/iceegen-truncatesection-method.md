---
title: ICeeGen::TruncateSection メソッド
ms.date: 03/30/2017
api_name:
- ICeeGen.TruncateSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::TruncateSection
helpviewer_keywords:
- TruncateSection method [.NET Framework metadata]
- ICeeGen::TruncateSection method [.NET Framework metadata]
ms.assetid: 0451d752-1e5c-4c9a-8bad-6cd35b7ba3df
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1036d6080bf17eea288724c7980ce53dfa2121f7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59116322"
---
# <a name="iceegentruncatesection-method"></a><span data-ttu-id="cbf2e-102">ICeeGen::TruncateSection メソッド</span><span class="sxs-lookup"><span data-stu-id="cbf2e-102">ICeeGen::TruncateSection Method</span></span>
<span data-ttu-id="cbf2e-103">指定された長さでは、指定したコードのセクションを切り捨てます。</span><span class="sxs-lookup"><span data-stu-id="cbf2e-103">Truncates the specified code section by the specified length.</span></span>  
  
 <span data-ttu-id="cbf2e-104">このメソッドは廃止され、使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbf2e-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbf2e-105">構文</span><span class="sxs-lookup"><span data-stu-id="cbf2e-105">Syntax</span></span>  
  
```  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cbf2e-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cbf2e-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="cbf2e-107">[in]切り捨てるセクション。</span><span class="sxs-lookup"><span data-stu-id="cbf2e-107">[in] The section to truncate.</span></span>  
  
 `len`  
 <span data-ttu-id="cbf2e-108">[in]セクションの切り捨てに使用する、バイト単位の長さ。</span><span class="sxs-lookup"><span data-stu-id="cbf2e-108">[in] The length, in bytes, by which to truncate the section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cbf2e-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="cbf2e-109">Remarks</span></span>  
 <span data-ttu-id="cbf2e-110">呼び出す`TruncateSection`別の方法で処理されない特別なセクションの要件がある場合にのみです。</span><span class="sxs-lookup"><span data-stu-id="cbf2e-110">Call `TruncateSection` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbf2e-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="cbf2e-111">Requirements</span></span>  
 <span data-ttu-id="cbf2e-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbf2e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbf2e-113">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cbf2e-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cbf2e-114">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="cbf2e-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="cbf2e-115">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="cbf2e-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cbf2e-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="cbf2e-116">See also</span></span>

- [<span data-ttu-id="cbf2e-117">ICeeGen インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cbf2e-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
