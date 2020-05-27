---
title: StackOverflowType 列挙型
ms.date: 03/30/2017
api_name:
- StackOverflowType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StackOverflowType
helpviewer_keywords:
- StackOverflowType enumeration [.NET Framework hosting]
ms.assetid: dab648ad-972b-479c-b129-b4c1dcbd932e
topic_type:
- apiref
ms.openlocfilehash: f399d33dbe05cb5768aa45533ef30d28409e18e2
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006468"
---
# <a name="stackoverflowtype-enumeration"></a><span data-ttu-id="46f09-102">StackOverflowType 列挙型</span><span class="sxs-lookup"><span data-stu-id="46f09-102">StackOverflowType Enumeration</span></span>
<span data-ttu-id="46f09-103">スタックオーバーフローイベントの根底にある原因を示す値を格納します。</span><span class="sxs-lookup"><span data-stu-id="46f09-103">Contains values that indicate the underlying cause of a stack overflow event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46f09-104">構文</span><span class="sxs-lookup"><span data-stu-id="46f09-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    SO_Managed,  
    SO_ClrEngine,  
    SO_Other  
} StackOverflowType;  
```  
  
## <a name="members"></a><span data-ttu-id="46f09-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="46f09-105">Members</span></span>  
  
|<span data-ttu-id="46f09-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="46f09-106">Member</span></span>|<span data-ttu-id="46f09-107">説明</span><span class="sxs-lookup"><span data-stu-id="46f09-107">Description</span></span>|  
|------------|-----------------|  
|`SO_ClrEngine`|<span data-ttu-id="46f09-108">スタックオーバーフローは、実行エンジンによって発生しました。</span><span class="sxs-lookup"><span data-stu-id="46f09-108">The stack overflow was caused by the execution engine.</span></span>|  
|`SO_Managed`|<span data-ttu-id="46f09-109">スタックオーバーフローは、マネージコードによって発生しました。</span><span class="sxs-lookup"><span data-stu-id="46f09-109">The stack overflow was caused by managed code.</span></span>|  
|`SO_Other`|<span data-ttu-id="46f09-110">スタックオーバーフローは、アンマネージコードによって発生しました。</span><span class="sxs-lookup"><span data-stu-id="46f09-110">The stack overflow was caused by unmanaged code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46f09-111">コメント</span><span class="sxs-lookup"><span data-stu-id="46f09-111">Remarks</span></span>  
 <span data-ttu-id="46f09-112">この情報は、 [Iactiononclrevent:: OnEvent](iactiononclrevent-onevent-method.md)メソッドの呼び出しによってホストに渡されます。</span><span class="sxs-lookup"><span data-stu-id="46f09-112">This information is passed to the host through a call to the [IActionOnCLREvent::OnEvent](iactiononclrevent-onevent-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46f09-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="46f09-113">Requirements</span></span>  
 <span data-ttu-id="46f09-114">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46f09-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46f09-115">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="46f09-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="46f09-116">**ライブラリ:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="46f09-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="46f09-117">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46f09-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46f09-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="46f09-118">See also</span></span>

- [<span data-ttu-id="46f09-119">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="46f09-119">Hosting Enumerations</span></span>](hosting-enumerations.md)
