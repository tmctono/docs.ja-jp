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
ms.openlocfilehash: 129750644962cee3206b9e38cbeaa77d38dddd71
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176111"
---
# <a name="iceegenaddsectionreloc-method"></a><span data-ttu-id="2890f-102">ICeeGen::AddSectionReloc メソッド</span><span class="sxs-lookup"><span data-stu-id="2890f-102">ICeeGen::AddSectionReloc Method</span></span>
<span data-ttu-id="2890f-103">コード ベースに .reloc 命令を追加します。</span><span class="sxs-lookup"><span data-stu-id="2890f-103">Adds a .reloc instruction to the code base.</span></span>  
  
 <span data-ttu-id="2890f-104">このメソッドは廃止され、使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="2890f-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2890f-105">構文</span><span class="sxs-lookup"><span data-stu-id="2890f-105">Syntax</span></span>  
  
```cpp  
HRESULT AddSectionReloc (  
   [in] HCEESECTION            section,  
   [in] ULONG                  offset,  
   [in] HCEESECTION            relativeTo,
   [in] CeeSectionRelocType    relocType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2890f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2890f-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="2890f-107">[in]reloc 命令を追加するメモリ内コードのセクション。</span><span class="sxs-lookup"><span data-stu-id="2890f-107">[in] The section of in-memory code to which to add a .reloc instruction.</span></span>  
  
 `offset`  
 <span data-ttu-id="2890f-108">[in]セクションのオフセット。</span><span class="sxs-lookup"><span data-stu-id="2890f-108">[in] The offset of the section.</span></span>  
  
 `relativeTo`  
 <span data-ttu-id="2890f-109">[in]参照先の`offset`セクション。</span><span class="sxs-lookup"><span data-stu-id="2890f-109">[in] The section to which `offset` refers.</span></span>  
  
 `relocType`  
 <span data-ttu-id="2890f-110">[in]追加する[.reloc](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md)命令の種類を示す、1 つの値です。</span><span class="sxs-lookup"><span data-stu-id="2890f-110">[in] One of the [CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md) values, indicating the kind of .reloc instruction to add.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2890f-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="2890f-111">Requirements</span></span>  
 <span data-ttu-id="2890f-112">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2890f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2890f-113">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="2890f-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2890f-114">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="2890f-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2890f-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2890f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2890f-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="2890f-116">See also</span></span>

- [<span data-ttu-id="2890f-117">ICeeGen インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2890f-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
