---
title: CorSaveSize 列挙型
ms.date: 03/30/2017
api_name:
- CorSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSaveSize
helpviewer_keywords:
- CorSaveSize enumeration [.NET Framework metadata]
ms.assetid: eb95ce39-5688-43c1-a34d-578794b32faa
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c1e7bbac17d9a9ae191a5ad6d69b52a806383562
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781609"
---
# <a name="corsavesize-enumeration"></a><span data-ttu-id="59d99-102">CorSaveSize 列挙型</span><span class="sxs-lookup"><span data-stu-id="59d99-102">CorSaveSize Enumeration</span></span>
<span data-ttu-id="59d99-103">保存操作のサイズの照会で要求される精度のレベルを示す値が格納されます。</span><span class="sxs-lookup"><span data-stu-id="59d99-103">Contains values indicating the level of precision required when querying for the size of a save operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59d99-104">構文</span><span class="sxs-lookup"><span data-stu-id="59d99-104">Syntax</span></span>  
  
```cpp  
typedef enum CorSaveSize {  
    cssAccurate                = 0x0000,   
    cssQuick                   = 0x0001,   
    cssDiscardTransientCAs     = 0x0002  
} CorSaveSize;  
```  
  
## <a name="members"></a><span data-ttu-id="59d99-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="59d99-105">Members</span></span>  
  
|<span data-ttu-id="59d99-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="59d99-106">Member</span></span>|<span data-ttu-id="59d99-107">説明</span><span class="sxs-lookup"><span data-stu-id="59d99-107">Description</span></span>|  
|------------|-----------------|  
|`cssAccurate`|<span data-ttu-id="59d99-108">戻り値が正確であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="59d99-108">Specifies that the return value should be exact.</span></span>|  
|`cssQuick`|<span data-ttu-id="59d99-109">戻り値を推定することを指定します。</span><span class="sxs-lookup"><span data-stu-id="59d99-109">Specifies that the return value should be estimated.</span></span>|  
|`cssDiscardTransientCAs`|<span data-ttu-id="59d99-110">破棄できる型を削除することを指定します。</span><span class="sxs-lookup"><span data-stu-id="59d99-110">Specifies that discardable types should be removed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="59d99-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="59d99-111">Requirements</span></span>  
 <span data-ttu-id="59d99-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="59d99-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59d99-113">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="59d99-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="59d99-114">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="59d99-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="59d99-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59d99-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59d99-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="59d99-116">See also</span></span>

- [<span data-ttu-id="59d99-117">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="59d99-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
