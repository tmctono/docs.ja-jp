---
title: COINITIEE 列挙型
ms.date: 03/30/2017
api_name:
- COINITIEE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COINITIEE
helpviewer_keywords:
- COINITIEE enumeration [.NET Framework metadata]
ms.assetid: 64264238-3b68-4bac-a887-36b552426a6c
topic_type:
- apiref
ms.openlocfilehash: 2ccc038b4420040779dae70f15e3a8827ba94180
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444102"
---
# <a name="coinitiee-enumeration"></a><span data-ttu-id="95bcd-102">COINITIEE 列挙型</span><span class="sxs-lookup"><span data-stu-id="95bcd-102">COINITIEE Enumeration</span></span>
<span data-ttu-id="95bcd-103">共通言語ランタイムを初期化するときに[Coinitializeee](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)によって使用される定数を指定します。</span><span class="sxs-lookup"><span data-stu-id="95bcd-103">Specifies constants used by [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95bcd-104">構文</span><span class="sxs-lookup"><span data-stu-id="95bcd-104">Syntax</span></span>  
  
```cpp  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="95bcd-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="95bcd-105">Members</span></span>  
  
|<span data-ttu-id="95bcd-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="95bcd-106">Member</span></span>|<span data-ttu-id="95bcd-107">説明</span><span class="sxs-lookup"><span data-stu-id="95bcd-107">Description</span></span>|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|<span data-ttu-id="95bcd-108">既定の初期化モード。</span><span class="sxs-lookup"><span data-stu-id="95bcd-108">Default initialization mode.</span></span> <span data-ttu-id="95bcd-109">これにより、ランタイムが初期化され、既定の <xref:System.AppDomain>が作成されます。</span><span class="sxs-lookup"><span data-stu-id="95bcd-109">This initializes the runtime and creates the default <xref:System.AppDomain>.</span></span>|  
|`COINITEE_DLL`|<span data-ttu-id="95bcd-110">マネージ DLL を実行するように初期化します。</span><span class="sxs-lookup"><span data-stu-id="95bcd-110">Initializes to run a managed DLL.</span></span>|  
|`COINITEE_MAIN`|<span data-ttu-id="95bcd-111">マネージ EXE を実行するように初期化します。</span><span class="sxs-lookup"><span data-stu-id="95bcd-111">Initializes to run a managed EXE.</span></span> <span data-ttu-id="95bcd-112">これにより、ランタイムが初期化されますが、既定の <xref:System.AppDomain>は作成されません。これは、EXE のメインルーチンを入力した後に作成されます。</span><span class="sxs-lookup"><span data-stu-id="95bcd-112">This initializes the runtime but does not create the default <xref:System.AppDomain>, which is created after entering the main routine of the EXE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="95bcd-113">要件</span><span class="sxs-lookup"><span data-stu-id="95bcd-113">Requirements</span></span>  
 <span data-ttu-id="95bcd-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95bcd-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95bcd-115">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="95bcd-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="95bcd-116">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="95bcd-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="95bcd-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95bcd-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95bcd-118">参照</span><span class="sxs-lookup"><span data-stu-id="95bcd-118">See also</span></span>

- [<span data-ttu-id="95bcd-119">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="95bcd-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
