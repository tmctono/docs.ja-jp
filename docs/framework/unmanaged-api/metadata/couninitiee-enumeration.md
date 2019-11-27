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
ms.openlocfilehash: 57054bdb7e3b991bc81985c02ec72a4110f31d60
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436436"
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="4d404-102">COUNINITIEE 列挙型</span><span class="sxs-lookup"><span data-stu-id="4d404-102">COUNINITIEE Enumeration</span></span>
<span data-ttu-id="4d404-103">共通言語ランタイムを初期化するときに[CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md)によって使用される定数を指定します。</span><span class="sxs-lookup"><span data-stu-id="4d404-103">Specifies constants used by [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d404-104">構文</span><span class="sxs-lookup"><span data-stu-id="4d404-104">Syntax</span></span>  
  
```cpp  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,   
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="4d404-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="4d404-105">Members</span></span>  
  
|<span data-ttu-id="4d404-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="4d404-106">Member</span></span>|<span data-ttu-id="4d404-107">説明</span><span class="sxs-lookup"><span data-stu-id="4d404-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="4d404-108">既定の初期化解除中モードを示します。</span><span class="sxs-lookup"><span data-stu-id="4d404-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="4d404-109">アセンブリをアンロードするための初期化解除中モードを示します。</span><span class="sxs-lookup"><span data-stu-id="4d404-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4d404-110">要件</span><span class="sxs-lookup"><span data-stu-id="4d404-110">Requirements</span></span>  
 <span data-ttu-id="4d404-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d404-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d404-112">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="4d404-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4d404-113">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="4d404-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4d404-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d404-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d404-115">参照</span><span class="sxs-lookup"><span data-stu-id="4d404-115">See also</span></span>

- [<span data-ttu-id="4d404-116">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="4d404-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
