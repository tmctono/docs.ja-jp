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
ms.openlocfilehash: 206dcd3a0a82da9b6211c8c2045e4e9d3d991973
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008873"
---
# <a name="iceegencomputepointer-method"></a><span data-ttu-id="ba366-102">ICeeGen::ComputePointer メソッド</span><span class="sxs-lookup"><span data-stu-id="ba366-102">ICeeGen::ComputePointer Method</span></span>
<span data-ttu-id="ba366-103">指定されたコードセクションのバッファーを決定します。</span><span class="sxs-lookup"><span data-stu-id="ba366-103">Determines the buffer for the specified code section.</span></span>  
  
 <span data-ttu-id="ba366-104">このメソッドは互換性のために残されています。使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="ba366-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba366-105">構文</span><span class="sxs-lookup"><span data-stu-id="ba366-105">Syntax</span></span>  
  
```cpp  
HRESULT ComputePointer (  
    [in]  HCEESECTION  section,  
    [in]  ULONG        RVA,
    [out] UCHAR        **lpBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba366-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ba366-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="ba366-107">からバッファーを返す対象のコードセクション。</span><span class="sxs-lookup"><span data-stu-id="ba366-107">[in] The code section for which to return a buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="ba366-108">からポインターを取得するメソッドの相対仮想アドレス。</span><span class="sxs-lookup"><span data-stu-id="ba366-108">[in] The relative virtual address of the method for which to get a pointer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="ba366-109">入出力返されたバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="ba366-109">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba366-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="ba366-110">Requirements</span></span>  
 <span data-ttu-id="ba366-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba366-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba366-112">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="ba366-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ba366-113">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="ba366-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ba366-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba366-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba366-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="ba366-115">See also</span></span>

- [<span data-ttu-id="ba366-116">ICeeGen インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ba366-116">ICeeGen Interface</span></span>](iceegen-interface.md)
