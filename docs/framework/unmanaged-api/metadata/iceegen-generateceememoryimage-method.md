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
ms.openlocfilehash: 4de3530cb912f9e60a6bdf11026f9168a188c8ce
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008824"
---
# <a name="iceegengenerateceememoryimage-method"></a><span data-ttu-id="df4a6-102">ICeeGen::GenerateCeeMemoryImage メソッド</span><span class="sxs-lookup"><span data-stu-id="df4a6-102">ICeeGen::GenerateCeeMemoryImage Method</span></span>
<span data-ttu-id="df4a6-103">コードベースのイメージをメモリ内に生成します。</span><span class="sxs-lookup"><span data-stu-id="df4a6-103">Generates an image in memory for the code base.</span></span>  
  
 <span data-ttu-id="df4a6-104">このメソッドは互換性のために残されています。使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="df4a6-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df4a6-105">構文</span><span class="sxs-lookup"><span data-stu-id="df4a6-105">Syntax</span></span>  
  
```cpp  
HRESULT GenerateCeeMemoryImage (  
    [out] void    **ppImage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df4a6-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="df4a6-106">Parameters</span></span>  
 `ppImage`  
 <span data-ttu-id="df4a6-107">入出力生成されたイメージへのポインター。</span><span class="sxs-lookup"><span data-stu-id="df4a6-107">[out] A pointer to the generated image.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df4a6-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="df4a6-108">Requirements</span></span>  
 <span data-ttu-id="df4a6-109">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df4a6-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df4a6-110">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="df4a6-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="df4a6-111">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="df4a6-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="df4a6-112">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df4a6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df4a6-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="df4a6-113">See also</span></span>

- [<span data-ttu-id="df4a6-114">ICeeGen インターフェイス</span><span class="sxs-lookup"><span data-stu-id="df4a6-114">ICeeGen Interface</span></span>](iceegen-interface.md)
