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
ms.openlocfilehash: 9587bbe8f087fd9a51bba67492af1d5acb53ae4a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176098"
---
# <a name="iceegencomputepointer-method"></a><span data-ttu-id="3625d-102">ICeeGen::ComputePointer メソッド</span><span class="sxs-lookup"><span data-stu-id="3625d-102">ICeeGen::ComputePointer Method</span></span>
<span data-ttu-id="3625d-103">指定したコード セクションのバッファーを決定します。</span><span class="sxs-lookup"><span data-stu-id="3625d-103">Determines the buffer for the specified code section.</span></span>  
  
 <span data-ttu-id="3625d-104">このメソッドは廃止され、使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="3625d-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3625d-105">構文</span><span class="sxs-lookup"><span data-stu-id="3625d-105">Syntax</span></span>  
  
```cpp  
HRESULT ComputePointer (  
    [in]  HCEESECTION  section,  
    [in]  ULONG        RVA,
    [out] UCHAR        **lpBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3625d-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3625d-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="3625d-107">[in]バッファーを返すコード セクション。</span><span class="sxs-lookup"><span data-stu-id="3625d-107">[in] The code section for which to return a buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="3625d-108">[in]ポインターを取得するメソッドの相対仮想アドレス。</span><span class="sxs-lookup"><span data-stu-id="3625d-108">[in] The relative virtual address of the method for which to get a pointer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="3625d-109">[アウト]返されたバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3625d-109">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3625d-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="3625d-110">Requirements</span></span>  
 <span data-ttu-id="3625d-111">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3625d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3625d-112">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="3625d-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3625d-113">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="3625d-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3625d-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3625d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3625d-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="3625d-115">See also</span></span>

- [<span data-ttu-id="3625d-116">ICeeGen インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3625d-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
