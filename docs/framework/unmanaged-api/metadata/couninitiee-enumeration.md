---
title: COUNINITIEE 列挙型
ms.date: 03/30/2017
api_name:
- COUNINITIEE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COUNINITIEE
helpviewer_keywords:
- COUNINITIEE enumeration [.NET Framework metadata]
ms.assetid: c42baa79-f469-4330-95a2-baf7f021c2fc
topic_type:
- apiref
ms.openlocfilehash: e5cbd8c5b1bb048088fe137b1359d0bb9e29af20
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176124"
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="a9041-102">COUNINITIEE 列挙型</span><span class="sxs-lookup"><span data-stu-id="a9041-102">COUNINITIEE Enumeration</span></span>
<span data-ttu-id="a9041-103">共通言語ランタイムの初期化時に[CoUninitializeE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md)によって使用される定数を指定します。</span><span class="sxs-lookup"><span data-stu-id="a9041-103">Specifies constants used by [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9041-104">構文</span><span class="sxs-lookup"><span data-stu-id="a9041-104">Syntax</span></span>  
  
```cpp  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="a9041-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="a9041-105">Members</span></span>  
  
|<span data-ttu-id="a9041-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="a9041-106">Member</span></span>|<span data-ttu-id="a9041-107">説明</span><span class="sxs-lookup"><span data-stu-id="a9041-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="a9041-108">既定の初期化解除モードを示します。</span><span class="sxs-lookup"><span data-stu-id="a9041-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="a9041-109">アセンブリをアンロードするための初期化解除モードを示します。</span><span class="sxs-lookup"><span data-stu-id="a9041-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a9041-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="a9041-110">Requirements</span></span>  
 <span data-ttu-id="a9041-111">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9041-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9041-112">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="a9041-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a9041-113">**ライブラリ:** MsCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="a9041-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a9041-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9041-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9041-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="a9041-115">See also</span></span>

- [<span data-ttu-id="a9041-116">メタデータ列挙体</span><span class="sxs-lookup"><span data-stu-id="a9041-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
