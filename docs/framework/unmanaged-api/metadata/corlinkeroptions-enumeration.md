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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045795"
---
# <a name="corlinkeroptions-enumeration"></a><span data-ttu-id="0fb45-102">CorLinkerOptions 列挙型</span><span class="sxs-lookup"><span data-stu-id="0fb45-102">CorLinkerOptions Enumeration</span></span>
<span data-ttu-id="0fb45-103">メタデータ リンカーのオプションを選択するためのフラグを指定します。</span><span class="sxs-lookup"><span data-stu-id="0fb45-103">Specifies flags to select options for the metadata linker.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fb45-104">構文</span><span class="sxs-lookup"><span data-stu-id="0fb45-104">Syntax</span></span>  
  
```  
typedef enum CorLinkerOptions {  
    MDAssembly          = 0x00000000,  
    MDNetModule         = 0x00000001,  
} CorLinkerOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="0fb45-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="0fb45-105">Members</span></span>  
  
|<span data-ttu-id="0fb45-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="0fb45-106">Member</span></span>|<span data-ttu-id="0fb45-107">説明</span><span class="sxs-lookup"><span data-stu-id="0fb45-107">Description</span></span>|  
|------------|-----------------|  
|`MDAssembly`|<span data-ttu-id="0fb45-108">プライベート型とグローバル関数は保持されません。</span><span class="sxs-lookup"><span data-stu-id="0fb45-108">The private types and global functions are not preserved.</span></span>|  
|`MDNetModule`|<span data-ttu-id="0fb45-109">プライベート型とグローバル関数が保持されます。</span><span class="sxs-lookup"><span data-stu-id="0fb45-109">The private types and global functions are preserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0fb45-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="0fb45-110">Requirements</span></span>  
 <span data-ttu-id="0fb45-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0fb45-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fb45-112">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="0fb45-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="0fb45-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fb45-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fb45-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="0fb45-114">See also</span></span>

- [<span data-ttu-id="0fb45-115">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="0fb45-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
