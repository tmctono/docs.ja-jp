---
title: ICeeGen::EmitString メソッド
ms.date: 03/30/2017
api_name:
- ICeeGen.EmitString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::EmitString
helpviewer_keywords:
- EmitString method [.NET Framework metadata]
- ICeeGen::EmitString method [.NET Framework metadata]
ms.assetid: ad2710a7-edb8-4493-8619-3fce235e3334
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1eabf5631fcfe7a187d0e203d64c7a7f4f5a819a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59209958"
---
# <a name="iceegenemitstring-method"></a><span data-ttu-id="2483c-102">ICeeGen::EmitString メソッド</span><span class="sxs-lookup"><span data-stu-id="2483c-102">ICeeGen::EmitString Method</span></span>
<span data-ttu-id="2483c-103">コード ベースに、指定した文字列を出力します。</span><span class="sxs-lookup"><span data-stu-id="2483c-103">Emits the specified string into the code base.</span></span>  
  
 <span data-ttu-id="2483c-104">このメソッドは廃止され、使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2483c-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2483c-105">構文</span><span class="sxs-lookup"><span data-stu-id="2483c-105">Syntax</span></span>  
  
```  
HRESULT EmitString (  
    [in]  LPWSTR    lpString,  
    [out] ULONG     *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2483c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2483c-106">Parameters</span></span>  
 `lpString`  
 <span data-ttu-id="2483c-107">[in]出力する文字列。</span><span class="sxs-lookup"><span data-stu-id="2483c-107">[in] The string to emit.</span></span>  
  
 `RVA`  
 <span data-ttu-id="2483c-108">[out]生成された文字列の相対仮想アドレス。</span><span class="sxs-lookup"><span data-stu-id="2483c-108">[out] The relative virtual address of the emitted string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2483c-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="2483c-109">Requirements</span></span>  
 <span data-ttu-id="2483c-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2483c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2483c-111">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2483c-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2483c-112">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="2483c-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2483c-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2483c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2483c-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="2483c-114">See also</span></span>

- [<span data-ttu-id="2483c-115">ICeeGen インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2483c-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
