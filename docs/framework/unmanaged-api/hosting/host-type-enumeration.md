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
ms.openlocfilehash: dfb1cff3e95c5ff86d22913745b7d14982766b48
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175228"
---
# <a name="hosttype-enumeration"></a><span data-ttu-id="546cd-102">HOST_TYPE 列挙型</span><span class="sxs-lookup"><span data-stu-id="546cd-102">HOST_TYPE Enumeration</span></span>
<span data-ttu-id="546cd-103">アプリケーションを起動するホストの種類を指定する値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="546cd-103">Contains values that specify the type of host that is launching an application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="546cd-104">構文</span><span class="sxs-lookup"><span data-stu-id="546cd-104">Syntax</span></span>  
  
```  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="546cd-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="546cd-105">Members</span></span>  
  
|<span data-ttu-id="546cd-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="546cd-106">Member</span></span>|<span data-ttu-id="546cd-107">説明</span><span class="sxs-lookup"><span data-stu-id="546cd-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|<span data-ttu-id="546cd-108">AppLaunch.exe からアプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="546cd-108">Launch the application from AppLaunch.exe.</span></span><br /><br /> <span data-ttu-id="546cd-109">部分的に信頼されたアプリケーションには、この値を使用します。</span><span class="sxs-lookup"><span data-stu-id="546cd-109">Use this value for partially-trusted applications.</span></span>|  
|`HOST_TYPE_CORFLAG`|<span data-ttu-id="546cd-110">アプリケーションを直接起動します。</span><span class="sxs-lookup"><span data-stu-id="546cd-110">Launch the application directly.</span></span> <span data-ttu-id="546cd-111">つまり、独自の .exe ファイルからアプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="546cd-111">That is, launch the application from its own .exe file.</span></span><br /><br /> <span data-ttu-id="546cd-112">完全に信頼されたアプリケーションには、この値を使用します。</span><span class="sxs-lookup"><span data-stu-id="546cd-112">Use this value for fully-trusted applications.</span></span>|  
|`HOST_TYPE_DEFAULT`|<span data-ttu-id="546cd-113">HOST_TYPE_APPLAUNCH と同じです。</span><span class="sxs-lookup"><span data-stu-id="546cd-113">Same as HOST_TYPE_APPLAUNCH.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="546cd-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="546cd-114">Requirements</span></span>  
 <span data-ttu-id="546cd-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="546cd-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="546cd-116">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="546cd-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="546cd-117">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="546cd-117">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="546cd-118">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="546cd-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="546cd-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="546cd-119">See also</span></span>

- [<span data-ttu-id="546cd-120">ホスティングの列挙体</span><span class="sxs-lookup"><span data-stu-id="546cd-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
