---
title: ICeeGen::GetSectionBlock メソッド
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionBlock
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionBlock
helpviewer_keywords:
- GetSectionBlock method [.NET Framework metadata]
- ICeeGen::GetSectionBlock method [.NET Framework metadata]
ms.assetid: 05c78aaf-5bbd-497e-9ae2-55f4fae0c5fb
topic_type:
- apiref
ms.openlocfilehash: ed534890fc90d3b8543a1166c85903f10163f0a8
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008327"
---
# <a name="iceegengetsectionblock-method"></a><span data-ttu-id="5ac31-102">ICeeGen::GetSectionBlock メソッド</span><span class="sxs-lookup"><span data-stu-id="5ac31-102">ICeeGen::GetSectionBlock Method</span></span>
<span data-ttu-id="5ac31-103">コードベースのセクションブロックを取得します。</span><span class="sxs-lookup"><span data-stu-id="5ac31-103">Gets a section block of the code base.</span></span>  
  
 <span data-ttu-id="5ac31-104">このメソッドは互換性のために残されています。使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="5ac31-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ac31-105">構文</span><span class="sxs-lookup"><span data-stu-id="5ac31-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSectionBlock (  
    [in]  HCEESECTION    section,
    [in]  ULONG          len,  
    [in]  ULONG          align     = 1,  
    [out] void           **ppBytes = 0  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="5ac31-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5ac31-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="5ac31-107">からコードベースのブロックを取得する対象となるセクション。</span><span class="sxs-lookup"><span data-stu-id="5ac31-107">[in] The section from which to retrieve a block of the code base.</span></span>  
  
 `len`  
 <span data-ttu-id="5ac31-108">から取得するブロックの長さ。</span><span class="sxs-lookup"><span data-stu-id="5ac31-108">[in] The length of the block to be retrieved.</span></span>  
  
 `align`  
 <span data-ttu-id="5ac31-109">からブロックの最初のバイトを揃えるために使用する、セクションの先頭を基準とするバイト。</span><span class="sxs-lookup"><span data-stu-id="5ac31-109">[in] The byte, relative to the beginning of the section, with which to align the first byte of the block.</span></span> <span data-ttu-id="5ac31-110">これは、セクション内のブロックの位置です。</span><span class="sxs-lookup"><span data-stu-id="5ac31-110">This is the position of the block within the section.</span></span>  
  
 `ppBytes`  
 <span data-ttu-id="5ac31-111">入出力取得されたブロックのアドレスを受け取る場所へのポインター。</span><span class="sxs-lookup"><span data-stu-id="5ac31-111">[out] A pointer to a location that receives the address of the retrieved block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ac31-112">コメント</span><span class="sxs-lookup"><span data-stu-id="5ac31-112">Remarks</span></span>  
 <span data-ttu-id="5ac31-113">`GetSectionBlock`他のメソッドによって処理されない特殊なセクション要件がある場合にのみ、を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="5ac31-113">Call `GetSectionBlock` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ac31-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="5ac31-114">Requirements</span></span>  
 <span data-ttu-id="5ac31-115">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ac31-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ac31-116">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="5ac31-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5ac31-117">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="5ac31-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5ac31-118">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ac31-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ac31-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="5ac31-119">See also</span></span>

- [<span data-ttu-id="5ac31-120">ICeeGen インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5ac31-120">ICeeGen Interface</span></span>](iceegen-interface.md)
