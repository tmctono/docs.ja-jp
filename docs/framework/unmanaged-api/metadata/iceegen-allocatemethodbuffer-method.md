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
ms.openlocfilehash: 8dc7f439cac56c2d55916ff8631ec3095c67680d
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008886"
---
# <a name="iceegenallocatemethodbuffer-method"></a><span data-ttu-id="6aa90-102">ICeeGen::AllocateMethodBuffer メソッド</span><span class="sxs-lookup"><span data-stu-id="6aa90-102">ICeeGen::AllocateMethodBuffer Method</span></span>
<span data-ttu-id="6aa90-103">メソッドに対して指定したサイズのバッファーを作成し、メソッドの相対仮想アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="6aa90-103">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>  
  
 <span data-ttu-id="6aa90-104">このメソッドは互換性のために残されています。使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="6aa90-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6aa90-105">構文</span><span class="sxs-lookup"><span data-stu-id="6aa90-105">Syntax</span></span>  
  
```cpp  
HRESULT AllocateMethodBuffer (
    [in]  ULONG    cchBuffer,
    [out] UCHAR    **lpBuffer,  
    [out] ULONG    *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6aa90-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6aa90-106">Parameters</span></span>  
 `cchBuffer`  
 <span data-ttu-id="6aa90-107">から作成するバッファーの長さ。</span><span class="sxs-lookup"><span data-stu-id="6aa90-107">[in] The length of the buffer to create.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="6aa90-108">入出力返されたバッファー。</span><span class="sxs-lookup"><span data-stu-id="6aa90-108">[out] The returned buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="6aa90-109">入出力メソッドの相対仮想アドレス。</span><span class="sxs-lookup"><span data-stu-id="6aa90-109">[out] The relative virtual address of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6aa90-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="6aa90-110">Requirements</span></span>  
 <span data-ttu-id="6aa90-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6aa90-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6aa90-112">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="6aa90-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6aa90-113">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="6aa90-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6aa90-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6aa90-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aa90-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="6aa90-115">See also</span></span>

- [<span data-ttu-id="6aa90-116">ICeeGen インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6aa90-116">ICeeGen Interface</span></span>](iceegen-interface.md)
