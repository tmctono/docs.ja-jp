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
ms.openlocfilehash: f4d1c2f105abb64bf196d0dd8371c2788c97336e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005909"
---
# <a name="coinitiee-enumeration"></a><span data-ttu-id="70916-102">COINITIEE 列挙型</span><span class="sxs-lookup"><span data-stu-id="70916-102">COINITIEE Enumeration</span></span>
<span data-ttu-id="70916-103">共通言語ランタイムを初期化するときに[Coinitializeee](../hosting/coinitializeee-function.md)によって使用される定数を指定します。</span><span class="sxs-lookup"><span data-stu-id="70916-103">Specifies constants used by [CoInitializeEE](../hosting/coinitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70916-104">構文</span><span class="sxs-lookup"><span data-stu-id="70916-104">Syntax</span></span>  
  
```cpp  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="70916-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="70916-105">Members</span></span>  
  
|<span data-ttu-id="70916-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="70916-106">Member</span></span>|<span data-ttu-id="70916-107">説明</span><span class="sxs-lookup"><span data-stu-id="70916-107">Description</span></span>|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|<span data-ttu-id="70916-108">既定の初期化モード。</span><span class="sxs-lookup"><span data-stu-id="70916-108">Default initialization mode.</span></span> <span data-ttu-id="70916-109">これにより、ランタイムが初期化され、既定値が作成され <xref:System.AppDomain> ます。</span><span class="sxs-lookup"><span data-stu-id="70916-109">This initializes the runtime and creates the default <xref:System.AppDomain>.</span></span>|  
|`COINITEE_DLL`|<span data-ttu-id="70916-110">マネージ DLL を実行するように初期化します。</span><span class="sxs-lookup"><span data-stu-id="70916-110">Initializes to run a managed DLL.</span></span>|  
|`COINITEE_MAIN`|<span data-ttu-id="70916-111">マネージ EXE を実行するように初期化します。</span><span class="sxs-lookup"><span data-stu-id="70916-111">Initializes to run a managed EXE.</span></span> <span data-ttu-id="70916-112">これにより、ランタイムが初期化されますが、既定値は作成されません <xref:System.AppDomain> 。これは、EXE のメインルーチンを入力した後に作成されます。</span><span class="sxs-lookup"><span data-stu-id="70916-112">This initializes the runtime but does not create the default <xref:System.AppDomain>, which is created after entering the main routine of the EXE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="70916-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="70916-113">Requirements</span></span>  
 <span data-ttu-id="70916-114">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70916-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70916-115">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="70916-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="70916-116">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="70916-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="70916-117">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70916-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70916-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="70916-118">See also</span></span>

- [<span data-ttu-id="70916-119">メタデータ列挙体</span><span class="sxs-lookup"><span data-stu-id="70916-119">Metadata Enumerations</span></span>](metadata-enumerations.md)
