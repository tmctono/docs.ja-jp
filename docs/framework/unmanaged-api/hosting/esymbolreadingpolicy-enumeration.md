---
title: ESymbolReadingPolicy 列挙型
ms.date: 03/30/2017
api_name:
- ESymbolReadingPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ESymbolReadingPolicy
helpviewer_keywords:
- ESymbolReadingPolicy enumeration [.NET Framework hosting]
ms.assetid: 4dc6c80d-b694-480b-a378-d5b18420ce17
topic_type:
- apiref
ms.openlocfilehash: 786ff6895383fc18dcfedb26fab344f80f04c1df
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138208"
---
# <a name="esymbolreadingpolicy-enumeration"></a><span data-ttu-id="334a5-102">ESymbolReadingPolicy 列挙型</span><span class="sxs-lookup"><span data-stu-id="334a5-102">ESymbolReadingPolicy Enumeration</span></span>
<span data-ttu-id="334a5-103">プログラムデータベース (PDB) ファイルを読み取るためのポリシーを設定する値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="334a5-103">Contains values that set the policy for reading program database (PDB) files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="334a5-104">構文</span><span class="sxs-lookup"><span data-stu-id="334a5-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="334a5-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="334a5-105">Members</span></span>  
  
|<span data-ttu-id="334a5-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="334a5-106">Member</span></span>|<span data-ttu-id="334a5-107">説明</span><span class="sxs-lookup"><span data-stu-id="334a5-107">Description</span></span>|  
|------------|-----------------|  
|`eSymbolReadingAlways`|<span data-ttu-id="334a5-108">デバッガーが常に PDB ファイルを読み取る必要があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="334a5-108">Specifies that the debugger should always read PDB files.</span></span>|  
|`eSymbolReadingFullTrustOnly`|<span data-ttu-id="334a5-109">デバッガーが、完全に信頼されたアセンブリに関連付けられている PDB ファイルのみを読み取るように指定します。</span><span class="sxs-lookup"><span data-stu-id="334a5-109">Specifies that the debugger should read only PDB files that are associated with full-trust assemblies.</span></span>|  
|`eSymbolReadingNever`|<span data-ttu-id="334a5-110">デバッガーが PDB ファイルを読み取らないように指定します。</span><span class="sxs-lookup"><span data-stu-id="334a5-110">Specifies that the debugger should never read PDB files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="334a5-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="334a5-111">Remarks</span></span>  
 <span data-ttu-id="334a5-112">`ESymbolReadingPolicy` 列挙体は、 [ICLRDebugManager:: SetSymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md)メソッドと共に使用されます。</span><span class="sxs-lookup"><span data-stu-id="334a5-112">The `ESymbolReadingPolicy` enumeration is used with the [ICLRDebugManager::SetSymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="334a5-113">［要件］</span><span class="sxs-lookup"><span data-stu-id="334a5-113">Requirements</span></span>  
 <span data-ttu-id="334a5-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="334a5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="334a5-115">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="334a5-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="334a5-116">**ライブラリ:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="334a5-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="334a5-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="334a5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="334a5-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="334a5-118">See also</span></span>

- [<span data-ttu-id="334a5-119">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="334a5-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
