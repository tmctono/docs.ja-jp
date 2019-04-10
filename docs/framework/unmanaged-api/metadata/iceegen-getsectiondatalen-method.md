---
title: ICeeGen::GetSectionDataLen メソッド
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionDataLen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionDataLen
helpviewer_keywords:
- ICeeGen::GetSectionDataLen method [.NET Framework metadata]
- GetSectionDataLen method [.NET Framework metadata]
ms.assetid: e2a06ee4-b8ee-49c7-935a-c1031a29eef2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ca01f78cf46d4f7543b949c820eb6b1971687e23
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198713"
---
# <a name="iceegengetsectiondatalen-method"></a><span data-ttu-id="31865-102">ICeeGen::GetSectionDataLen メソッド</span><span class="sxs-lookup"><span data-stu-id="31865-102">ICeeGen::GetSectionDataLen Method</span></span>
<span data-ttu-id="31865-103">指定されたセクションの長さを取得します。</span><span class="sxs-lookup"><span data-stu-id="31865-103">Gets the length of the specified section.</span></span>  
  
 <span data-ttu-id="31865-104">このメソッドは廃止され、使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31865-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31865-105">構文</span><span class="sxs-lookup"><span data-stu-id="31865-105">Syntax</span></span>  
  
```  
HRESULT GetSectionDataLen (  
    [in]  HCEESECTION  section,  
    [out] ULONG        *dataLen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31865-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="31865-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="31865-107">[in]データ セクションは、長さが取得されます。</span><span class="sxs-lookup"><span data-stu-id="31865-107">[in] The data section whose length will be retrieved.</span></span>  
  
 `dataLen`  
 <span data-ttu-id="31865-108">[out]返される、指定されたセクションの長さ。</span><span class="sxs-lookup"><span data-stu-id="31865-108">[out] The returned length of the specified section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="31865-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="31865-109">Remarks</span></span>  
 <span data-ttu-id="31865-110">呼び出す`GetSectionDataLen`別の方法で処理されない特別なセクションの要件がある場合にのみです。</span><span class="sxs-lookup"><span data-stu-id="31865-110">Call `GetSectionDataLen` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31865-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="31865-111">Requirements</span></span>  
 <span data-ttu-id="31865-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="31865-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31865-113">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="31865-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="31865-114">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="31865-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="31865-115">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="31865-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="31865-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="31865-116">See also</span></span>

- [<span data-ttu-id="31865-117">ICeeGen インターフェイス</span><span class="sxs-lookup"><span data-stu-id="31865-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
