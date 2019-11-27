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
ms.openlocfilehash: 0731053fb37c775d25052a5fd99a479a44ff5862
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434883"
---
# <a name="iceegengetsectionblock-method"></a><span data-ttu-id="75b9d-102">ICeeGen::GetSectionBlock メソッド</span><span class="sxs-lookup"><span data-stu-id="75b9d-102">ICeeGen::GetSectionBlock Method</span></span>
<span data-ttu-id="75b9d-103">コードベースのセクションブロックを取得します。</span><span class="sxs-lookup"><span data-stu-id="75b9d-103">Gets a section block of the code base.</span></span>  
  
 <span data-ttu-id="75b9d-104">このメソッドは互換性のために残されています。使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="75b9d-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75b9d-105">構文</span><span class="sxs-lookup"><span data-stu-id="75b9d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSectionBlock (  
    [in]  HCEESECTION    section,     
    [in]  ULONG          len,  
    [in]  ULONG          align     = 1,  
    [out] void           **ppBytes = 0  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="75b9d-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="75b9d-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="75b9d-107">からコードベースのブロックを取得する対象となるセクション。</span><span class="sxs-lookup"><span data-stu-id="75b9d-107">[in] The section from which to retrieve a block of the code base.</span></span>  
  
 `len`  
 <span data-ttu-id="75b9d-108">から取得するブロックの長さ。</span><span class="sxs-lookup"><span data-stu-id="75b9d-108">[in] The length of the block to be retrieved.</span></span>  
  
 `align`  
 <span data-ttu-id="75b9d-109">からブロックの最初のバイトを揃えるために使用する、セクションの先頭を基準とするバイト。</span><span class="sxs-lookup"><span data-stu-id="75b9d-109">[in] The byte, relative to the beginning of the section, with which to align the first byte of the block.</span></span> <span data-ttu-id="75b9d-110">これは、セクション内のブロックの位置です。</span><span class="sxs-lookup"><span data-stu-id="75b9d-110">This is the position of the block within the section.</span></span>  
  
 `ppBytes`  
 <span data-ttu-id="75b9d-111">入出力取得されたブロックのアドレスを受け取る場所へのポインター。</span><span class="sxs-lookup"><span data-stu-id="75b9d-111">[out] A pointer to a location that receives the address of the retrieved block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75b9d-112">コメント</span><span class="sxs-lookup"><span data-stu-id="75b9d-112">Remarks</span></span>  
 <span data-ttu-id="75b9d-113">他のメソッドによって処理されない特殊なセクション要件がある場合にのみ、`GetSectionBlock` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="75b9d-113">Call `GetSectionBlock` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75b9d-114">要件</span><span class="sxs-lookup"><span data-stu-id="75b9d-114">Requirements</span></span>  
 <span data-ttu-id="75b9d-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75b9d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75b9d-116">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="75b9d-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="75b9d-117">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="75b9d-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="75b9d-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75b9d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75b9d-119">参照</span><span class="sxs-lookup"><span data-stu-id="75b9d-119">See also</span></span>

- [<span data-ttu-id="75b9d-120">ICeeGen インターフェイス</span><span class="sxs-lookup"><span data-stu-id="75b9d-120">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
