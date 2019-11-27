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
ms.openlocfilehash: 34636f1ca8e42c452aa41f6145d439a26f01b0a7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436395"
---
# <a name="iceegenallocatemethodbuffer-method"></a><span data-ttu-id="af2c2-102">ICeeGen::AllocateMethodBuffer メソッド</span><span class="sxs-lookup"><span data-stu-id="af2c2-102">ICeeGen::AllocateMethodBuffer Method</span></span>
<span data-ttu-id="af2c2-103">メソッドに対して指定したサイズのバッファーを作成し、メソッドの相対仮想アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="af2c2-103">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>  
  
 <span data-ttu-id="af2c2-104">このメソッドは互換性のために残されています。使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="af2c2-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af2c2-105">構文</span><span class="sxs-lookup"><span data-stu-id="af2c2-105">Syntax</span></span>  
  
```cpp  
HRESULT AllocateMethodBuffer (   
    [in]  ULONG    cchBuffer,   
    [out] UCHAR    **lpBuffer,  
    [out] ULONG    *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af2c2-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="af2c2-106">Parameters</span></span>  
 `cchBuffer`  
 <span data-ttu-id="af2c2-107">から作成するバッファーの長さ。</span><span class="sxs-lookup"><span data-stu-id="af2c2-107">[in] The length of the buffer to create.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="af2c2-108">入出力返されたバッファー。</span><span class="sxs-lookup"><span data-stu-id="af2c2-108">[out] The returned buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="af2c2-109">入出力メソッドの相対仮想アドレス。</span><span class="sxs-lookup"><span data-stu-id="af2c2-109">[out] The relative virtual address of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af2c2-110">要件</span><span class="sxs-lookup"><span data-stu-id="af2c2-110">Requirements</span></span>  
 <span data-ttu-id="af2c2-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af2c2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af2c2-112">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="af2c2-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="af2c2-113">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="af2c2-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="af2c2-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af2c2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af2c2-115">参照</span><span class="sxs-lookup"><span data-stu-id="af2c2-115">See also</span></span>

- [<span data-ttu-id="af2c2-116">ICeeGen インターフェイス</span><span class="sxs-lookup"><span data-stu-id="af2c2-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
