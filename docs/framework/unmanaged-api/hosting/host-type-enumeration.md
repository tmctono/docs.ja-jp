---
title: HOST_TYPE 列挙型
ms.date: 03/30/2017
api_name:
- HOST_TYPE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- HOST_TYPE
helpviewer_keywords:
- HOST_TYPE enumeration [.NET Framework hosting]
ms.assetid: 51f848be-84c5-4036-9839-c762c576bbf5
topic_type:
- apiref
ms.openlocfilehash: e8dda83df8a320733f45dbcc13599cdf37d26492
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617153"
---
# <a name="host_type-enumeration"></a><span data-ttu-id="351d7-102">HOST_TYPE 列挙型</span><span class="sxs-lookup"><span data-stu-id="351d7-102">HOST_TYPE Enumeration</span></span>
<span data-ttu-id="351d7-103">アプリケーションを起動しているホストの種類を指定する値を格納します。</span><span class="sxs-lookup"><span data-stu-id="351d7-103">Contains values that specify the type of host that is launching an application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="351d7-104">構文</span><span class="sxs-lookup"><span data-stu-id="351d7-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="351d7-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="351d7-105">Members</span></span>  
  
|<span data-ttu-id="351d7-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="351d7-106">Member</span></span>|<span data-ttu-id="351d7-107">説明</span><span class="sxs-lookup"><span data-stu-id="351d7-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|<span data-ttu-id="351d7-108">AppLaunch からアプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="351d7-108">Launch the application from AppLaunch.exe.</span></span><br /><br /> <span data-ttu-id="351d7-109">部分的に信頼されたアプリケーションには、この値を使用します。</span><span class="sxs-lookup"><span data-stu-id="351d7-109">Use this value for partially-trusted applications.</span></span>|  
|`HOST_TYPE_CORFLAG`|<span data-ttu-id="351d7-110">アプリケーションを直接起動します。</span><span class="sxs-lookup"><span data-stu-id="351d7-110">Launch the application directly.</span></span> <span data-ttu-id="351d7-111">つまり、アプリケーションを独自の .exe ファイルから起動します。</span><span class="sxs-lookup"><span data-stu-id="351d7-111">That is, launch the application from its own .exe file.</span></span><br /><br /> <span data-ttu-id="351d7-112">この値は、完全に信頼されたアプリケーションに使用します。</span><span class="sxs-lookup"><span data-stu-id="351d7-112">Use this value for fully-trusted applications.</span></span>|  
|`HOST_TYPE_DEFAULT`|<span data-ttu-id="351d7-113">HOST_TYPE_APPLAUNCH と同じです。</span><span class="sxs-lookup"><span data-stu-id="351d7-113">Same as HOST_TYPE_APPLAUNCH.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="351d7-114">要件</span><span class="sxs-lookup"><span data-stu-id="351d7-114">Requirements</span></span>  
 <span data-ttu-id="351d7-115">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="351d7-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="351d7-116">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="351d7-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="351d7-117">**ライブラリ:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="351d7-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="351d7-118">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="351d7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="351d7-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="351d7-119">See also</span></span>

- [<span data-ttu-id="351d7-120">ホスティングの列挙体</span><span class="sxs-lookup"><span data-stu-id="351d7-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
