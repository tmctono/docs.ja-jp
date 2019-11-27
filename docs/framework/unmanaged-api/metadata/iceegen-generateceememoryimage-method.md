---
title: ICeeGen::GenerateCeeMemoryImage メソッド
ms.date: 03/30/2017
api_name:
- ICeeGen.GenerateCeeMemoryImage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GenerateCeeMemoryImage
helpviewer_keywords:
- ICeeGen::GenerateCeeMemoryImage method [.NET Framework metadata]
- GenerateCeeMemoryImage method [.NET Framework metadata]
ms.assetid: b3847495-0ae6-4a72-b496-65ce2424afc6
topic_type:
- apiref
ms.openlocfilehash: a15b9bf5612e18196fc57266d60ec7be3691c682
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436359"
---
# <a name="iceegengenerateceememoryimage-method"></a><span data-ttu-id="658b2-102">ICeeGen::GenerateCeeMemoryImage メソッド</span><span class="sxs-lookup"><span data-stu-id="658b2-102">ICeeGen::GenerateCeeMemoryImage Method</span></span>
<span data-ttu-id="658b2-103">コードベースのイメージをメモリ内に生成します。</span><span class="sxs-lookup"><span data-stu-id="658b2-103">Generates an image in memory for the code base.</span></span>  
  
 <span data-ttu-id="658b2-104">このメソッドは互換性のために残されています。使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="658b2-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="658b2-105">構文</span><span class="sxs-lookup"><span data-stu-id="658b2-105">Syntax</span></span>  
  
```cpp  
HRESULT GenerateCeeMemoryImage (  
    [out] void    **ppImage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="658b2-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="658b2-106">Parameters</span></span>  
 `ppImage`  
 <span data-ttu-id="658b2-107">入出力生成されたイメージへのポインター。</span><span class="sxs-lookup"><span data-stu-id="658b2-107">[out] A pointer to the generated image.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="658b2-108">要件</span><span class="sxs-lookup"><span data-stu-id="658b2-108">Requirements</span></span>  
 <span data-ttu-id="658b2-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="658b2-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="658b2-110">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="658b2-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="658b2-111">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="658b2-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="658b2-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="658b2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="658b2-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="658b2-113">See also</span></span>

- [<span data-ttu-id="658b2-114">ICeeGen インターフェイス</span><span class="sxs-lookup"><span data-stu-id="658b2-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
