---
title: CorLinkerOptions 列挙型
ms.date: 03/30/2017
api_name:
- CorLinkerOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorLinkerOptions
helpviewer_keywords:
- CorLinkerOptions enumeration [.NET Framework metadata]
ms.assetid: a656aad6-cc7e-4994-8251-004a6a45e18f
topic_type:
- apiref
ms.openlocfilehash: 086e17185df9caa823b44b51cf027f95d635c48d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450275"
---
# <a name="corlinkeroptions-enumeration"></a><span data-ttu-id="6cbeb-102">CorLinkerOptions 列挙型</span><span class="sxs-lookup"><span data-stu-id="6cbeb-102">CorLinkerOptions Enumeration</span></span>
<span data-ttu-id="6cbeb-103">メタデータ リンカーのオプションを選択するためのフラグを指定します。</span><span class="sxs-lookup"><span data-stu-id="6cbeb-103">Specifies flags to select options for the metadata linker.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cbeb-104">構文</span><span class="sxs-lookup"><span data-stu-id="6cbeb-104">Syntax</span></span>  
  
```cpp  
typedef enum CorLinkerOptions {  
    MDAssembly          = 0x00000000,  
    MDNetModule         = 0x00000001,  
} CorLinkerOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="6cbeb-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="6cbeb-105">Members</span></span>  
  
|<span data-ttu-id="6cbeb-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="6cbeb-106">Member</span></span>|<span data-ttu-id="6cbeb-107">説明</span><span class="sxs-lookup"><span data-stu-id="6cbeb-107">Description</span></span>|  
|------------|-----------------|  
|`MDAssembly`|<span data-ttu-id="6cbeb-108">The private types and global functions are not preserved.</span><span class="sxs-lookup"><span data-stu-id="6cbeb-108">The private types and global functions are not preserved.</span></span>|  
|`MDNetModule`|<span data-ttu-id="6cbeb-109">The private types and global functions are preserved.</span><span class="sxs-lookup"><span data-stu-id="6cbeb-109">The private types and global functions are preserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6cbeb-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="6cbeb-110">Requirements</span></span>  
 <span data-ttu-id="6cbeb-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6cbeb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6cbeb-112">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="6cbeb-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="6cbeb-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6cbeb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cbeb-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="6cbeb-114">See also</span></span>

- [<span data-ttu-id="6cbeb-115">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="6cbeb-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
