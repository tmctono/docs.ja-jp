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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dc0554ed89d21607978d059b26c4ad69e59a2d4c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59166635"
---
# <a name="corlinkeroptions-enumeration"></a><span data-ttu-id="fccd7-102">CorLinkerOptions 列挙型</span><span class="sxs-lookup"><span data-stu-id="fccd7-102">CorLinkerOptions Enumeration</span></span>
<span data-ttu-id="fccd7-103">メタデータ リンカーのオプションを選択するためのフラグを指定します。</span><span class="sxs-lookup"><span data-stu-id="fccd7-103">Specifies flags to select options for the metadata linker.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fccd7-104">構文</span><span class="sxs-lookup"><span data-stu-id="fccd7-104">Syntax</span></span>  
  
```  
typedef enum CorLinkerOptions {  
    MDAssembly          = 0x00000000,  
    MDNetModule         = 0x00000001,  
} CorLinkerOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="fccd7-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="fccd7-105">Members</span></span>  
  
|<span data-ttu-id="fccd7-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="fccd7-106">Member</span></span>|<span data-ttu-id="fccd7-107">説明</span><span class="sxs-lookup"><span data-stu-id="fccd7-107">Description</span></span>|  
|------------|-----------------|  
|`MDAssembly`|<span data-ttu-id="fccd7-108">プライベート型とグローバル関数は保持されません。</span><span class="sxs-lookup"><span data-stu-id="fccd7-108">The private types and global functions are not preserved.</span></span>|  
|`MDNetModule`|<span data-ttu-id="fccd7-109">プライベート型とグローバル関数が保持されます。</span><span class="sxs-lookup"><span data-stu-id="fccd7-109">The private types and global functions are preserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fccd7-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="fccd7-110">Requirements</span></span>  
 <span data-ttu-id="fccd7-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fccd7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fccd7-112">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="fccd7-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="fccd7-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fccd7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fccd7-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="fccd7-114">See also</span></span>

- [<span data-ttu-id="fccd7-115">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="fccd7-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
