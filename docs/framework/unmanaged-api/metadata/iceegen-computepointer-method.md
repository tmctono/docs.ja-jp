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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992629"
---
# <a name="iceegencomputepointer-method"></a><span data-ttu-id="8ab35-102">ICeeGen::ComputePointer メソッド</span><span class="sxs-lookup"><span data-stu-id="8ab35-102">ICeeGen::ComputePointer Method</span></span>
<span data-ttu-id="8ab35-103">指定したコードのセクションのバッファーを決定します。</span><span class="sxs-lookup"><span data-stu-id="8ab35-103">Determines the buffer for the specified code section.</span></span>  
  
 <span data-ttu-id="8ab35-104">このメソッドは廃止され、使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ab35-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ab35-105">構文</span><span class="sxs-lookup"><span data-stu-id="8ab35-105">Syntax</span></span>  
  
```  
HRESULT ComputePointer (  
    [in]  HCEESECTION  section,  
    [in]  ULONG        RVA,   
    [out] UCHAR        **lpBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ab35-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8ab35-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="8ab35-107">[in]バッファーを返す対象のコード セクション。</span><span class="sxs-lookup"><span data-stu-id="8ab35-107">[in] The code section for which to return a buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="8ab35-108">[in]ポインターを取得する対象のメソッドの相対仮想アドレス。</span><span class="sxs-lookup"><span data-stu-id="8ab35-108">[in] The relative virtual address of the method for which to get a pointer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="8ab35-109">[out]返されたバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8ab35-109">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ab35-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="8ab35-110">Requirements</span></span>  
 <span data-ttu-id="8ab35-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ab35-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ab35-112">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8ab35-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8ab35-113">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="8ab35-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8ab35-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ab35-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ab35-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="8ab35-115">See also</span></span>

- [<span data-ttu-id="8ab35-116">ICeeGen インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8ab35-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
