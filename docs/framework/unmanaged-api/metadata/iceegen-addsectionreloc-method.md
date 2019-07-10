---
title: ICeeGen::AddSectionReloc メソッド
ms.date: 03/30/2017
api_name:
- ICeeGen.AddSectionReloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::AddSectionReloc
helpviewer_keywords:
- AddSectionReloc method [.NET Framework metadata]
- ICeeGen::AddSectionReloc method [.NET Framework metadata]
ms.assetid: b500a260-1d57-4953-95e1-c27063f7c8da
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: da3b83191ce1acdf40e27c5ee1d843a1fb4a54f8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750676"
---
# <a name="iceegenaddsectionreloc-method"></a><span data-ttu-id="270d7-102">ICeeGen::AddSectionReloc メソッド</span><span class="sxs-lookup"><span data-stu-id="270d7-102">ICeeGen::AddSectionReloc Method</span></span>
<span data-ttu-id="270d7-103">コード ベースを .reloc 命令を追加します。</span><span class="sxs-lookup"><span data-stu-id="270d7-103">Adds a .reloc instruction to the code base.</span></span>  
  
 <span data-ttu-id="270d7-104">このメソッドは廃止され、使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="270d7-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="270d7-105">構文</span><span class="sxs-lookup"><span data-stu-id="270d7-105">Syntax</span></span>  
  
```cpp  
HRESULT AddSectionReloc (  
   [in] HCEESECTION            section,  
   [in] ULONG                  offset,  
   [in] HCEESECTION            relativeTo,   
   [in] CeeSectionRelocType    relocType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="270d7-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="270d7-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="270d7-107">[in].Reloc 命令を追加するメモリ内のコードのセクション。</span><span class="sxs-lookup"><span data-stu-id="270d7-107">[in] The section of in-memory code to which to add a .reloc instruction.</span></span>  
  
 `offset`  
 <span data-ttu-id="270d7-108">[in]このセクションのオフセット。</span><span class="sxs-lookup"><span data-stu-id="270d7-108">[in] The offset of the section.</span></span>  
  
 `relativeTo`  
 <span data-ttu-id="270d7-109">[in]セクション`offset`参照します。</span><span class="sxs-lookup"><span data-stu-id="270d7-109">[in] The section to which `offset` refers.</span></span>  
  
 `relocType`  
 <span data-ttu-id="270d7-110">[in]1 つ、 [CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md)を追加する .reloc 命令の種類を示す値。</span><span class="sxs-lookup"><span data-stu-id="270d7-110">[in] One of the [CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md) values, indicating the kind of .reloc instruction to add.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="270d7-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="270d7-111">Requirements</span></span>  
 <span data-ttu-id="270d7-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="270d7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="270d7-113">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="270d7-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="270d7-114">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="270d7-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="270d7-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="270d7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="270d7-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="270d7-116">See also</span></span>

- [<span data-ttu-id="270d7-117">ICeeGen インターフェイス</span><span class="sxs-lookup"><span data-stu-id="270d7-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
