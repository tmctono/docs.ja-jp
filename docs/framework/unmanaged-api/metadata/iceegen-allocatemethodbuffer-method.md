---
title: ICeeGen::AllocateMethodBuffer メソッド
ms.date: 03/30/2017
api_name:
- ICeeGen.AllocateMethodBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::AllocateMethodBuffer
helpviewer_keywords:
- AllocateMethodBuffer method [.NET Framework metadata]
- ICeeGen::AllocateMethodBuffer method [.NET Framework metadata]
ms.assetid: 845ab77e-9639-47f5-99fb-f3b619e3e779
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 080c16d3a7baceaa277b3418ac2e17391090f00c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750595"
---
# <a name="iceegenallocatemethodbuffer-method"></a><span data-ttu-id="a52b0-102">ICeeGen::AllocateMethodBuffer メソッド</span><span class="sxs-lookup"><span data-stu-id="a52b0-102">ICeeGen::AllocateMethodBuffer Method</span></span>
<span data-ttu-id="a52b0-103">メソッドで指定されたサイズのバッファーを作成し、メソッドの相対仮想アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="a52b0-103">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>  
  
 <span data-ttu-id="a52b0-104">このメソッドは廃止され、使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a52b0-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a52b0-105">構文</span><span class="sxs-lookup"><span data-stu-id="a52b0-105">Syntax</span></span>  
  
```cpp  
HRESULT AllocateMethodBuffer (   
    [in]  ULONG    cchBuffer,   
    [out] UCHAR    **lpBuffer,  
    [out] ULONG    *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a52b0-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a52b0-106">Parameters</span></span>  
 `cchBuffer`  
 <span data-ttu-id="a52b0-107">[in]作成するバッファーの長さ。</span><span class="sxs-lookup"><span data-stu-id="a52b0-107">[in] The length of the buffer to create.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="a52b0-108">[out]返されたバッファー。</span><span class="sxs-lookup"><span data-stu-id="a52b0-108">[out] The returned buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="a52b0-109">[out]メソッドの相対仮想アドレス。</span><span class="sxs-lookup"><span data-stu-id="a52b0-109">[out] The relative virtual address of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a52b0-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="a52b0-110">Requirements</span></span>  
 <span data-ttu-id="a52b0-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a52b0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a52b0-112">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a52b0-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a52b0-113">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="a52b0-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a52b0-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a52b0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a52b0-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="a52b0-115">See also</span></span>

- [<span data-ttu-id="a52b0-116">ICeeGen インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a52b0-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
