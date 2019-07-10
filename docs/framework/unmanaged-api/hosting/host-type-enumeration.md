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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: caf76fa7962de9392b06591777ac862aa548d20d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779548"
---
# <a name="hosttype-enumeration"></a><span data-ttu-id="f77b7-102">HOST_TYPE 列挙型</span><span class="sxs-lookup"><span data-stu-id="f77b7-102">HOST_TYPE Enumeration</span></span>
<span data-ttu-id="f77b7-103">アプリケーションを起動するホストの種類を指定する値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f77b7-103">Contains values that specify the type of host that is launching an application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f77b7-104">構文</span><span class="sxs-lookup"><span data-stu-id="f77b7-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="f77b7-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="f77b7-105">Members</span></span>  
  
|<span data-ttu-id="f77b7-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="f77b7-106">Member</span></span>|<span data-ttu-id="f77b7-107">説明</span><span class="sxs-lookup"><span data-stu-id="f77b7-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|<span data-ttu-id="f77b7-108">AppLaunch.exe からアプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="f77b7-108">Launch the application from AppLaunch.exe.</span></span><br /><br /> <span data-ttu-id="f77b7-109">部分的に信頼されたアプリケーションには、この値を使用します。</span><span class="sxs-lookup"><span data-stu-id="f77b7-109">Use this value for partially-trusted applications.</span></span>|  
|`HOST_TYPE_CORFLAG`|<span data-ttu-id="f77b7-110">アプリケーションを直接起動します。</span><span class="sxs-lookup"><span data-stu-id="f77b7-110">Launch the application directly.</span></span> <span data-ttu-id="f77b7-111">つまり、独自の .exe ファイルからアプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="f77b7-111">That is, launch the application from its own .exe file.</span></span><br /><br /> <span data-ttu-id="f77b7-112">完全に信頼されたアプリケーションには、この値を使用します。</span><span class="sxs-lookup"><span data-stu-id="f77b7-112">Use this value for fully-trusted applications.</span></span>|  
|`HOST_TYPE_DEFAULT`|<span data-ttu-id="f77b7-113">HOST_TYPE_APPLAUNCH と同じです。</span><span class="sxs-lookup"><span data-stu-id="f77b7-113">Same as HOST_TYPE_APPLAUNCH.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f77b7-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="f77b7-114">Requirements</span></span>  
 <span data-ttu-id="f77b7-115">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f77b7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f77b7-116">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f77b7-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f77b7-117">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f77b7-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f77b7-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f77b7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f77b7-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="f77b7-119">See also</span></span>

- [<span data-ttu-id="f77b7-120">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="f77b7-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
