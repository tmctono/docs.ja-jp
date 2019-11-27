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
ms.openlocfilehash: e5940f229e86b46bb8c5d5b2f9920a8261359f65
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436412"
---
# <a name="iceegenaddsectionreloc-method"></a><span data-ttu-id="a7067-102">ICeeGen::AddSectionReloc メソッド</span><span class="sxs-lookup"><span data-stu-id="a7067-102">ICeeGen::AddSectionReloc Method</span></span>
<span data-ttu-id="a7067-103">コードベースに reloc 命令を追加します。</span><span class="sxs-lookup"><span data-stu-id="a7067-103">Adds a .reloc instruction to the code base.</span></span>  
  
 <span data-ttu-id="a7067-104">このメソッドは互換性のために残されています。使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="a7067-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7067-105">構文</span><span class="sxs-lookup"><span data-stu-id="a7067-105">Syntax</span></span>  
  
```cpp  
HRESULT AddSectionReloc (  
   [in] HCEESECTION            section,  
   [in] ULONG                  offset,  
   [in] HCEESECTION            relativeTo,   
   [in] CeeSectionRelocType    relocType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7067-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a7067-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="a7067-107">からReloc 命令を追加するメモリ内コードのセクション。</span><span class="sxs-lookup"><span data-stu-id="a7067-107">[in] The section of in-memory code to which to add a .reloc instruction.</span></span>  
  
 `offset`  
 <span data-ttu-id="a7067-108">からセクションのオフセット。</span><span class="sxs-lookup"><span data-stu-id="a7067-108">[in] The offset of the section.</span></span>  
  
 `relativeTo`  
 <span data-ttu-id="a7067-109">から`offset` が参照するセクション。</span><span class="sxs-lookup"><span data-stu-id="a7067-109">[in] The section to which `offset` refers.</span></span>  
  
 `relocType`  
 <span data-ttu-id="a7067-110">から[CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md)値の1つ。追加する reloc 命令の種類を示します。</span><span class="sxs-lookup"><span data-stu-id="a7067-110">[in] One of the [CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md) values, indicating the kind of .reloc instruction to add.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7067-111">要件</span><span class="sxs-lookup"><span data-stu-id="a7067-111">Requirements</span></span>  
 <span data-ttu-id="a7067-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7067-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7067-113">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="a7067-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a7067-114">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="a7067-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a7067-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7067-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7067-116">参照</span><span class="sxs-lookup"><span data-stu-id="a7067-116">See also</span></span>

- [<span data-ttu-id="a7067-117">ICeeGen インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a7067-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
