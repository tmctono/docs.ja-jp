---
title: MALLOC_TYPE 列挙体
ms.date: 03/30/2017
api_name:
- MALLOC_TYPE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- MALLOC_TYPE
helpviewer_keywords:
- MALLOC_TYPE Enumeration
ms.assetid: c02476f9-23a2-4af7-9282-aa9c42c7429b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 695f69c8d9c3a295a705971743733339cf8aab13
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59211947"
---
# <a name="malloctype-enumeration"></a><span data-ttu-id="479f2-102">MALLOC_TYPE 列挙体</span><span class="sxs-lookup"><span data-stu-id="479f2-102">MALLOC_TYPE Enumeration</span></span>
<span data-ttu-id="479f2-103">割り当てられるメモリの特性を指定する値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="479f2-103">Contains values that specify the characteristics of the memory that is being allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="479f2-104">構文</span><span class="sxs-lookup"><span data-stu-id="479f2-104">Syntax</span></span>  
  
```  
typedef enum {  
    MALLOC_THREADSAFE = 0x1,  
    MALLOC_EXECUTABLE = 0x2,  
} MALLOC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="479f2-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="479f2-105">Members</span></span>  
  
|<span data-ttu-id="479f2-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="479f2-106">Member</span></span>|<span data-ttu-id="479f2-107">説明</span><span class="sxs-lookup"><span data-stu-id="479f2-107">Description</span></span>|  
|------------|-----------------|  
|`MALLOC_EXECUTABLE`|<span data-ttu-id="479f2-108">割り当てられたメモリは、実行可能ファイルを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="479f2-108">The allocated memory can contain an executable file.</span></span>|  
|`MALLOC_THREADSAFE`|<span data-ttu-id="479f2-109">割り当てられたメモリは、スレッド セーフです。</span><span class="sxs-lookup"><span data-stu-id="479f2-109">The allocated memory is thread-safe.</span></span> <span data-ttu-id="479f2-110">つまり、メモリは、同期しなくても、複数のスレッドによってアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="479f2-110">That is, the memory can be accessed by multiple threads without any synchronization.</span></span><br /><br /> <span data-ttu-id="479f2-111">このフラグが設定されていない場合は、オブジェクトでの呼び出しをシリアル化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="479f2-111">If this flag is not set, calls on the object must be serialized.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="479f2-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="479f2-112">Requirements</span></span>  
 <span data-ttu-id="479f2-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="479f2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="479f2-114">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="479f2-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="479f2-115">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="479f2-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="479f2-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="479f2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="479f2-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="479f2-117">See also</span></span>

- [<span data-ttu-id="479f2-118">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="479f2-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
