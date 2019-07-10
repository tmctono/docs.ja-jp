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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 23f5a2b6b0970f3cb64ee339e6a1a409354a60e5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780952"
---
# <a name="coinitiee-enumeration"></a><span data-ttu-id="422ac-102">COINITIEE 列挙型</span><span class="sxs-lookup"><span data-stu-id="422ac-102">COINITIEE Enumeration</span></span>
<span data-ttu-id="422ac-103">使用される定数を指定します[CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)共通言語ランタイムを初期化するときにします。</span><span class="sxs-lookup"><span data-stu-id="422ac-103">Specifies constants used by [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="422ac-104">構文</span><span class="sxs-lookup"><span data-stu-id="422ac-104">Syntax</span></span>  
  
```cpp  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="422ac-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="422ac-105">Members</span></span>  
  
|<span data-ttu-id="422ac-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="422ac-106">Member</span></span>|<span data-ttu-id="422ac-107">説明</span><span class="sxs-lookup"><span data-stu-id="422ac-107">Description</span></span>|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|<span data-ttu-id="422ac-108">既定の初期化モード。</span><span class="sxs-lookup"><span data-stu-id="422ac-108">Default initialization mode.</span></span> <span data-ttu-id="422ac-109">ランタイムを初期化し、既定値を作成します。 この<xref:System.AppDomain>します。</span><span class="sxs-lookup"><span data-stu-id="422ac-109">This initializes the runtime and creates the default <xref:System.AppDomain>.</span></span>|  
|`COINITEE_DLL`|<span data-ttu-id="422ac-110">マネージ DLL を実行することを初期化します。</span><span class="sxs-lookup"><span data-stu-id="422ac-110">Initializes to run a managed DLL.</span></span>|  
|`COINITEE_MAIN`|<span data-ttu-id="422ac-111">マネージ EXE を実行することを初期化します。</span><span class="sxs-lookup"><span data-stu-id="422ac-111">Initializes to run a managed EXE.</span></span> <span data-ttu-id="422ac-112">これは、ランタイムを初期化しますが、既定値は作成されません<xref:System.AppDomain>、これは、exe ファイルのメイン ルーチンを入力した後に作成されます。</span><span class="sxs-lookup"><span data-stu-id="422ac-112">This initializes the runtime but does not create the default <xref:System.AppDomain>, which is created after entering the main routine of the EXE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="422ac-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="422ac-113">Requirements</span></span>  
 <span data-ttu-id="422ac-114">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="422ac-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="422ac-115">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="422ac-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="422ac-116">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="422ac-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="422ac-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="422ac-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="422ac-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="422ac-118">See also</span></span>

- [<span data-ttu-id="422ac-119">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="422ac-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
