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
ms.openlocfilehash: 994f6668de3040cc9f2381356d6db06c18c9e984
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745885"
---
# <a name="iceegentruncatesection-method"></a><span data-ttu-id="a1d04-102">ICeeGen::TruncateSection メソッド</span><span class="sxs-lookup"><span data-stu-id="a1d04-102">ICeeGen::TruncateSection Method</span></span>
<span data-ttu-id="a1d04-103">指定された長さでは、指定したコードのセクションを切り捨てます。</span><span class="sxs-lookup"><span data-stu-id="a1d04-103">Truncates the specified code section by the specified length.</span></span>  
  
 <span data-ttu-id="a1d04-104">このメソッドは廃止され、使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1d04-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1d04-105">構文</span><span class="sxs-lookup"><span data-stu-id="a1d04-105">Syntax</span></span>  
  
```cpp  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1d04-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a1d04-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="a1d04-107">[in]切り捨てるセクション。</span><span class="sxs-lookup"><span data-stu-id="a1d04-107">[in] The section to truncate.</span></span>  
  
 `len`  
 <span data-ttu-id="a1d04-108">[in]セクションの切り捨てに使用する、バイト単位の長さ。</span><span class="sxs-lookup"><span data-stu-id="a1d04-108">[in] The length, in bytes, by which to truncate the section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1d04-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="a1d04-109">Remarks</span></span>  
 <span data-ttu-id="a1d04-110">呼び出す`TruncateSection`別の方法で処理されない特別なセクションの要件がある場合にのみです。</span><span class="sxs-lookup"><span data-stu-id="a1d04-110">Call `TruncateSection` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1d04-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="a1d04-111">Requirements</span></span>  
 <span data-ttu-id="a1d04-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1d04-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1d04-113">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a1d04-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a1d04-114">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="a1d04-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a1d04-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1d04-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1d04-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1d04-116">See also</span></span>

- [<span data-ttu-id="a1d04-117">ICeeGen インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a1d04-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
