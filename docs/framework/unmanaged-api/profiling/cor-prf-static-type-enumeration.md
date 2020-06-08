---
title: COR_PRF_STATIC_TYPE 列挙型
ms.date: 03/30/2017
api_name:
- COR_PRF_STATIC_TYPE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_STATIC_TYPE
helpviewer_keywords:
- COR_PRF_STATIC_TYPE enumeration [.NET Framework profiling]
ms.assetid: 441d7809-5b65-41a5-ba64-2910a8008315
topic_type:
- apiref
ms.openlocfilehash: 80d72aefc736054afcee152c55e941c0f8f3c6a8
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500768"
---
# <a name="cor_prf_static_type-enumeration"></a><span data-ttu-id="85645-102">COR_PRF_STATIC_TYPE 列挙型</span><span class="sxs-lookup"><span data-stu-id="85645-102">COR_PRF_STATIC_TYPE Enumeration</span></span>
<span data-ttu-id="85645-103">フィールドが静的であるかどうかを示し、静的な場合は、フィールドに適用される静的なクオリティを示します。</span><span class="sxs-lookup"><span data-stu-id="85645-103">Indicates whether a field is static and, if so, the static quality that applies to the field.</span></span> <span data-ttu-id="85645-104">これらの値は、ビットごとの OR 演算を使用して組み合わせて、フィールドに複数の異なる静的品質があることを示すことができます。</span><span class="sxs-lookup"><span data-stu-id="85645-104">These values can be combined using the bitwise OR operation to indicate that the field has multiple, different static qualities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85645-105">構文</span><span class="sxs-lookup"><span data-stu-id="85645-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_FIELD_NOT_A_STATIC = 0x0,  
    COR_PRF_FIELD_APP_DOMAIN_STATIC = 0x1,  
    COR_PRF_FIELD_THREAD_STATIC = 0x2,  
    COR_PRF_FIELD_CONTEXT_STATIC = 0x4,  
    COR_PRF_FIELD_RVA_STATIC = 0x8  
} COR_PRF_STATIC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="85645-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="85645-106">Members</span></span>  
  
|<span data-ttu-id="85645-107">メンバー</span><span class="sxs-lookup"><span data-stu-id="85645-107">Member</span></span>|<span data-ttu-id="85645-108">説明</span><span class="sxs-lookup"><span data-stu-id="85645-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FIELD_NOT_A_STATIC`|<span data-ttu-id="85645-109">フィールドは静的ではありません。</span><span class="sxs-lookup"><span data-stu-id="85645-109">The field is not static.</span></span>|  
|`COR_PRF_FIELD_APP_DOMAIN_STATIC`|<span data-ttu-id="85645-110">フィールドは [アプリケーションドメイン-静的] です。</span><span class="sxs-lookup"><span data-stu-id="85645-110">The field is application domain-static.</span></span>|  
|`COR_PRF_FIELD_THREAD_STATIC`|<span data-ttu-id="85645-111">フィールドはスレッド静的です。</span><span class="sxs-lookup"><span data-stu-id="85645-111">The field is thread-static.</span></span>|  
|`COR_PRF_FIELD_CONTEXT_STATIC`|<span data-ttu-id="85645-112">フィールドは、コンテキスト静的です。</span><span class="sxs-lookup"><span data-stu-id="85645-112">The field is context-static.</span></span>|  
|`COR_PRF_FIELD_RVA_STATIC`|<span data-ttu-id="85645-113">フィールドは、相対仮想アドレス (RVA)-static です。</span><span class="sxs-lookup"><span data-stu-id="85645-113">The field is relative virtual address (RVA)-static.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="85645-114">要件</span><span class="sxs-lookup"><span data-stu-id="85645-114">Requirements</span></span>  
 <span data-ttu-id="85645-115">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85645-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85645-116">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="85645-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="85645-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="85645-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="85645-118">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85645-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85645-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="85645-119">See also</span></span>

- [<span data-ttu-id="85645-120">列挙体のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="85645-120">Profiling Enumerations</span></span>](profiling-enumerations.md)
