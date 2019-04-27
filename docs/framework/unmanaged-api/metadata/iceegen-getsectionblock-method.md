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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7e600f29a9036bb28031bd7854bc8cbb34c4566a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61905490"
---
# <a name="iceegengetsectionblock-method"></a><span data-ttu-id="ba456-102">ICeeGen::GetSectionBlock メソッド</span><span class="sxs-lookup"><span data-stu-id="ba456-102">ICeeGen::GetSectionBlock Method</span></span>
<span data-ttu-id="ba456-103">コード ベースのセクションのブロックを取得します。</span><span class="sxs-lookup"><span data-stu-id="ba456-103">Gets a section block of the code base.</span></span>  
  
 <span data-ttu-id="ba456-104">このメソッドは廃止され、使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba456-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba456-105">構文</span><span class="sxs-lookup"><span data-stu-id="ba456-105">Syntax</span></span>  
  
```  
HRESULT GetSectionBlock (  
    [in]  HCEESECTION    section,     
    [in]  ULONG          len,  
    [in]  ULONG          align     = 1,  
    [out] void           **ppBytes = 0  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="ba456-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ba456-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="ba456-107">[in]コード ベースのブロックの取得元となるセクション。</span><span class="sxs-lookup"><span data-stu-id="ba456-107">[in] The section from which to retrieve a block of the code base.</span></span>  
  
 `len`  
 <span data-ttu-id="ba456-108">[in]取得するブロックの長さ。</span><span class="sxs-lookup"><span data-stu-id="ba456-108">[in] The length of the block to be retrieved.</span></span>  
  
 `align`  
 <span data-ttu-id="ba456-109">[in]ブロックの最初のバイトを揃えるセクションの先頭からの相対バイト。</span><span class="sxs-lookup"><span data-stu-id="ba456-109">[in] The byte, relative to the beginning of the section, with which to align the first byte of the block.</span></span> <span data-ttu-id="ba456-110">これは、セクション内のブロックの位置です。</span><span class="sxs-lookup"><span data-stu-id="ba456-110">This is the position of the block within the section.</span></span>  
  
 `ppBytes`  
 <span data-ttu-id="ba456-111">[out]取得されたブロックのアドレスを受け取る場所へのポインター。</span><span class="sxs-lookup"><span data-stu-id="ba456-111">[out] A pointer to a location that receives the address of the retrieved block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba456-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="ba456-112">Remarks</span></span>  
 <span data-ttu-id="ba456-113">呼び出す`GetSectionBlock`別の方法で処理されない特別なセクションの要件がある場合にのみです。</span><span class="sxs-lookup"><span data-stu-id="ba456-113">Call `GetSectionBlock` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba456-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="ba456-114">Requirements</span></span>  
 <span data-ttu-id="ba456-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba456-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba456-116">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ba456-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ba456-117">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="ba456-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ba456-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba456-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba456-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="ba456-119">See also</span></span>

- [<span data-ttu-id="ba456-120">ICeeGen インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ba456-120">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
