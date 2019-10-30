---
title: ASM_DISPLAY_FLAGS 列挙型
ms.date: 03/30/2017
api_name:
- ASM_DISPLAY_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASM_DISPLAY_FLAGS
helpviewer_keywords:
- ASM_DISPLAY_FLAGS enumeration [.NET Framework fusion]
ms.assetid: dbade6c9-9d26-4a79-9fd2-46108edd12d7
topic_type:
- apiref
ms.openlocfilehash: a34648bece3b14d6175168f45916ca04aeeef71d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109244"
---
# <a name="asm_display_flags-enumeration"></a><span data-ttu-id="c0910-102">ASM_DISPLAY_FLAGS 列挙型</span><span class="sxs-lookup"><span data-stu-id="c0910-102">ASM_DISPLAY_FLAGS Enumeration</span></span>
<span data-ttu-id="c0910-103">[IAssemblyName:: GetDisplayName](iassemblyname-getdisplayname-method.md)メソッドによって表示名が取得されるアセンブリのバージョン、ビルド、カルチャ、署名などを示します。</span><span class="sxs-lookup"><span data-stu-id="c0910-103">Indicates the version, build, culture, signature, and so on, of the assembly whose display name will be retrieved by the [IAssemblyName::GetDisplayName](iassemblyname-getdisplayname-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0910-104">構文</span><span class="sxs-lookup"><span data-stu-id="c0910-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
  
    ASM_DISPLAYF_VERSION                 = 0x01,  
    ASM_DISPLAYF_CULTURE                 = 0x02,  
    ASM_DISPLAYF_PUBLIC_KEY_TOKEN        = 0x04,  
    ASM_DISPLAYF_PUBLIC_KEY              = 0x08,  
    ASM_DISPLAYF_CUSTOM                  = 0x10,  
    ASM_DISPLAYF_PROCESSORARCHITECTURE   = 0x20,  
    ASM_DISPLAYF_LANGUAGEID              = 0x40,  
    ASM_DISPLAYF_RETARGET                = 0x80,  
    ASM_DISPLAYF_CONFIG_MASK             = 0x100,  
    ASM_DISPLAYF_MVID                    = 0x200,  
    ASM_DISPLAYF_FULL                    =   
                      ASM_DISPLAYF_VERSION           |   
                      ASM_DISPLAYF_CULTURE           |   
                      ASM_DISPLAYF_PUBLIC_KEY_TOKEN  |   
                      ASM_DISPLAYF_RETARGET          |   
                      ASM_DISPLAYF_PROCESSORARCHITECTURE  
  
} ASM_DISPLAY_FLAGS;  
```  
  
## <a name="remarks"></a><span data-ttu-id="c0910-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="c0910-105">Remarks</span></span>  
 <span data-ttu-id="c0910-106">`ASM_DISPLAYF_FULL` は、 [IAssemblyName](iassemblyname-interface.md)オブジェクトのバージョンに加えられた変更を反映します。</span><span class="sxs-lookup"><span data-stu-id="c0910-106">`ASM_DISPLAYF_FULL` reflects any changes made to the version of the [IAssemblyName](iassemblyname-interface.md) object.</span></span> <span data-ttu-id="c0910-107">戻り値が不変であると想定しないでください。</span><span class="sxs-lookup"><span data-stu-id="c0910-107">Do not assume that the returned value is immutable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0910-108">［要件］</span><span class="sxs-lookup"><span data-stu-id="c0910-108">Requirements</span></span>  
 <span data-ttu-id="c0910-109">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0910-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0910-110">**ヘッダー:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="c0910-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="c0910-111">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="c0910-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c0910-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0910-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0910-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0910-113">See also</span></span>

- [<span data-ttu-id="c0910-114">IAssemblyName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c0910-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="c0910-115">Fusion 列挙型</span><span class="sxs-lookup"><span data-stu-id="c0910-115">Fusion Enumerations</span></span>](fusion-enumerations.md)
