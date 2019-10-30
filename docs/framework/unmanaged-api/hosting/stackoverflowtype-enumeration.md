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
ms.openlocfilehash: f09c6bb79d7bd28f4d8b74237b6f343a07b79062
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141477"
---
# <a name="stackoverflowtype-enumeration"></a><span data-ttu-id="04efa-102">StackOverflowType 列挙型</span><span class="sxs-lookup"><span data-stu-id="04efa-102">StackOverflowType Enumeration</span></span>
<span data-ttu-id="04efa-103">スタックオーバーフローイベントの根底にある原因を示す値を格納します。</span><span class="sxs-lookup"><span data-stu-id="04efa-103">Contains values that indicate the underlying cause of a stack overflow event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04efa-104">構文</span><span class="sxs-lookup"><span data-stu-id="04efa-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    SO_Managed,  
    SO_ClrEngine,  
    SO_Other  
} StackOverflowType;  
```  
  
## <a name="members"></a><span data-ttu-id="04efa-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="04efa-105">Members</span></span>  
  
|<span data-ttu-id="04efa-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="04efa-106">Member</span></span>|<span data-ttu-id="04efa-107">説明</span><span class="sxs-lookup"><span data-stu-id="04efa-107">Description</span></span>|  
|------------|-----------------|  
|`SO_ClrEngine`|<span data-ttu-id="04efa-108">スタックオーバーフローは、実行エンジンによって発生しました。</span><span class="sxs-lookup"><span data-stu-id="04efa-108">The stack overflow was caused by the execution engine.</span></span>|  
|`SO_Managed`|<span data-ttu-id="04efa-109">スタックオーバーフローは、マネージコードによって発生しました。</span><span class="sxs-lookup"><span data-stu-id="04efa-109">The stack overflow was caused by managed code.</span></span>|  
|`SO_Other`|<span data-ttu-id="04efa-110">スタックオーバーフローは、アンマネージコードによって発生しました。</span><span class="sxs-lookup"><span data-stu-id="04efa-110">The stack overflow was caused by unmanaged code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04efa-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="04efa-111">Remarks</span></span>  
 <span data-ttu-id="04efa-112">この情報は、 [Iactiononclrevent:: OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md)メソッドの呼び出しによってホストに渡されます。</span><span class="sxs-lookup"><span data-stu-id="04efa-112">This information is passed to the host through a call to the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04efa-113">［要件］</span><span class="sxs-lookup"><span data-stu-id="04efa-113">Requirements</span></span>  
 <span data-ttu-id="04efa-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04efa-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04efa-115">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="04efa-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="04efa-116">**ライブラリ:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="04efa-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="04efa-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04efa-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04efa-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="04efa-118">See also</span></span>

- [<span data-ttu-id="04efa-119">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="04efa-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
