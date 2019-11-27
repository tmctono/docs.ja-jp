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
ms.openlocfilehash: 87a70587027f283ef5976089b3f2daf1204e68ec
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426137"
---
# <a name="iceegentruncatesection-method"></a><span data-ttu-id="76f0c-102">ICeeGen::TruncateSection メソッド</span><span class="sxs-lookup"><span data-stu-id="76f0c-102">ICeeGen::TruncateSection Method</span></span>
<span data-ttu-id="76f0c-103">指定したコードセクションを指定した長さだけ切り捨てます。</span><span class="sxs-lookup"><span data-stu-id="76f0c-103">Truncates the specified code section by the specified length.</span></span>  
  
 <span data-ttu-id="76f0c-104">このメソッドは互換性のために残されています。使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="76f0c-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76f0c-105">構文</span><span class="sxs-lookup"><span data-stu-id="76f0c-105">Syntax</span></span>  
  
```cpp  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76f0c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="76f0c-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="76f0c-107">から切り捨てるセクション。</span><span class="sxs-lookup"><span data-stu-id="76f0c-107">[in] The section to truncate.</span></span>  
  
 `len`  
 <span data-ttu-id="76f0c-108">からセクションを切り捨てる長さ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="76f0c-108">[in] The length, in bytes, by which to truncate the section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="76f0c-109">コメント</span><span class="sxs-lookup"><span data-stu-id="76f0c-109">Remarks</span></span>  
 <span data-ttu-id="76f0c-110">他のメソッドによって処理されない特殊なセクション要件がある場合にのみ、`TruncateSection` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="76f0c-110">Call `TruncateSection` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76f0c-111">要件</span><span class="sxs-lookup"><span data-stu-id="76f0c-111">Requirements</span></span>  
 <span data-ttu-id="76f0c-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76f0c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76f0c-113">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="76f0c-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="76f0c-114">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="76f0c-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="76f0c-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76f0c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76f0c-116">参照</span><span class="sxs-lookup"><span data-stu-id="76f0c-116">See also</span></span>

- [<span data-ttu-id="76f0c-117">ICeeGen インターフェイス</span><span class="sxs-lookup"><span data-stu-id="76f0c-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
