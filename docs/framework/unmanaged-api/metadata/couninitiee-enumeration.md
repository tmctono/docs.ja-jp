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
ms.openlocfilehash: 14942680a79c4d1fcc69092a4f752738db1fb0b0
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008918"
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="99704-102">COUNINITIEE 列挙型</span><span class="sxs-lookup"><span data-stu-id="99704-102">COUNINITIEE Enumeration</span></span>
<span data-ttu-id="99704-103">共通言語ランタイムを初期化するときに[CoUninitializeEE](../hosting/couninitializeee-function.md)によって使用される定数を指定します。</span><span class="sxs-lookup"><span data-stu-id="99704-103">Specifies constants used by [CoUninitializeEE](../hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99704-104">構文</span><span class="sxs-lookup"><span data-stu-id="99704-104">Syntax</span></span>  
  
```cpp  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="99704-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="99704-105">Members</span></span>  
  
|<span data-ttu-id="99704-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="99704-106">Member</span></span>|<span data-ttu-id="99704-107">説明</span><span class="sxs-lookup"><span data-stu-id="99704-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="99704-108">既定の初期化解除中モードを示します。</span><span class="sxs-lookup"><span data-stu-id="99704-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="99704-109">アセンブリをアンロードするための初期化解除中モードを示します。</span><span class="sxs-lookup"><span data-stu-id="99704-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="99704-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="99704-110">Requirements</span></span>  
 <span data-ttu-id="99704-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99704-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99704-112">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="99704-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="99704-113">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="99704-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="99704-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99704-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99704-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="99704-115">See also</span></span>

- [<span data-ttu-id="99704-116">メタデータ列挙体</span><span class="sxs-lookup"><span data-stu-id="99704-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
