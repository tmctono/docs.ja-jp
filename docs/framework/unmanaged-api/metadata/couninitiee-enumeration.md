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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0cf1bfa03fd14d6324af60781003a8072a267a7e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59102948"
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="813df-102">COUNINITIEE 列挙型</span><span class="sxs-lookup"><span data-stu-id="813df-102">COUNINITIEE Enumeration</span></span>
<span data-ttu-id="813df-103">使用される定数を指定します[CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md)共通言語ランタイムを初期化するときにします。</span><span class="sxs-lookup"><span data-stu-id="813df-103">Specifies constants used by [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="813df-104">構文</span><span class="sxs-lookup"><span data-stu-id="813df-104">Syntax</span></span>  
  
```  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,   
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="813df-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="813df-105">Members</span></span>  
  
|<span data-ttu-id="813df-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="813df-106">Member</span></span>|<span data-ttu-id="813df-107">説明</span><span class="sxs-lookup"><span data-stu-id="813df-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="813df-108">既定の初期化解除モードを示します。</span><span class="sxs-lookup"><span data-stu-id="813df-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="813df-109">アセンブリをアンロードするための初期化解除モードを示します。</span><span class="sxs-lookup"><span data-stu-id="813df-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="813df-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="813df-110">Requirements</span></span>  
 <span data-ttu-id="813df-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="813df-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="813df-112">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="813df-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="813df-113">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="813df-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="813df-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="813df-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="813df-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="813df-115">See also</span></span>

- [<span data-ttu-id="813df-116">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="813df-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
