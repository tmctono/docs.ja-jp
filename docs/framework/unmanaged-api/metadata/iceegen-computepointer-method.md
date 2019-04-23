---
title: ICeeGen::ComputePointer メソッド
ms.date: 03/30/2017
api_name:
- ICeeGen.ComputePointer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::ComputePointer
helpviewer_keywords:
- ICeeGen::ComputePointer method [.NET Framework metadata]
- ComputePointer method [.NET Framework metadata]
ms.assetid: b6b95c04-0f2c-4fcc-a8bc-3b1dcbdba731
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 79ef272e0c8afa0cd1942416c3a5eb9b825c2e6f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59145146"
---
# <a name="iceegencomputepointer-method"></a><span data-ttu-id="2c2e2-102">ICeeGen::ComputePointer メソッド</span><span class="sxs-lookup"><span data-stu-id="2c2e2-102">ICeeGen::ComputePointer Method</span></span>
<span data-ttu-id="2c2e2-103">指定したコードのセクションのバッファーを決定します。</span><span class="sxs-lookup"><span data-stu-id="2c2e2-103">Determines the buffer for the specified code section.</span></span>  
  
 <span data-ttu-id="2c2e2-104">このメソッドは廃止され、使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c2e2-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c2e2-105">構文</span><span class="sxs-lookup"><span data-stu-id="2c2e2-105">Syntax</span></span>  
  
```  
HRESULT ComputePointer (  
    [in]  HCEESECTION  section,  
    [in]  ULONG        RVA,   
    [out] UCHAR        **lpBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c2e2-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2c2e2-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="2c2e2-107">[in]バッファーを返す対象のコード セクション。</span><span class="sxs-lookup"><span data-stu-id="2c2e2-107">[in] The code section for which to return a buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="2c2e2-108">[in]ポインターを取得する対象のメソッドの相対仮想アドレス。</span><span class="sxs-lookup"><span data-stu-id="2c2e2-108">[in] The relative virtual address of the method for which to get a pointer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="2c2e2-109">[out]返されたバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="2c2e2-109">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c2e2-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="2c2e2-110">Requirements</span></span>  
 <span data-ttu-id="2c2e2-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c2e2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c2e2-112">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2c2e2-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2c2e2-113">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="2c2e2-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2c2e2-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c2e2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c2e2-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="2c2e2-115">See also</span></span>

- [<span data-ttu-id="2c2e2-116">ICeeGen インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2c2e2-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
