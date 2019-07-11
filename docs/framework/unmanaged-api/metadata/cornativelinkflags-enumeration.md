---
title: CorNativeLinkFlags 列挙型
ms.date: 03/30/2017
api_name:
- CorNativeLinkFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeLinkFlags
helpviewer_keywords:
- CorNativeLinkFlags enumeration [.NET Framework metadata]
ms.assetid: 8027df7c-cfad-4724-bda0-7538d9519070
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6be71878ba354ebe53b4b8b9b40db3222ec828f3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781738"
---
# <a name="cornativelinkflags-enumeration"></a><span data-ttu-id="c75ed-102">CorNativeLinkFlags 列挙型</span><span class="sxs-lookup"><span data-stu-id="c75ed-102">CorNativeLinkFlags Enumeration</span></span>
<span data-ttu-id="c75ed-103">ネイティブ コードをリンクするときに、リンカーが使用するフラグ値を提供します。</span><span class="sxs-lookup"><span data-stu-id="c75ed-103">Provides flag values used by the linker when linking native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c75ed-104">構文</span><span class="sxs-lookup"><span data-stu-id="c75ed-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{  
    nlfNone         = 0x00,  
    nlfLastError    = 0x01,  
    nlfNoMangle     = 0x02,  
    nlfMaxValue     = 0x03  
} CorNativeLinkFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="c75ed-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="c75ed-105">Members</span></span>  
  
|<span data-ttu-id="c75ed-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="c75ed-106">Member</span></span>|<span data-ttu-id="c75ed-107">説明</span><span class="sxs-lookup"><span data-stu-id="c75ed-107">Description</span></span>|  
|------------|-----------------|  
|`nlfNone`|<span data-ttu-id="c75ed-108">フラグがないことを示します。</span><span class="sxs-lookup"><span data-stu-id="c75ed-108">Indicates no flags.</span></span>|  
|`nlfLastError`|<span data-ttu-id="c75ed-109">示す、`setLastError`キーワード。</span><span class="sxs-lookup"><span data-stu-id="c75ed-109">Indicates a `setLastError` keyword.</span></span>|  
|`nlfNoMangle`|<span data-ttu-id="c75ed-110">示す、`nomangle`キーワード。</span><span class="sxs-lookup"><span data-stu-id="c75ed-110">Indicates a `nomangle` keyword.</span></span>|  
|`nlfMaxValue`|<span data-ttu-id="c75ed-111">使用しません。</span><span class="sxs-lookup"><span data-stu-id="c75ed-111">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c75ed-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="c75ed-112">Requirements</span></span>  
 <span data-ttu-id="c75ed-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c75ed-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c75ed-114">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c75ed-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c75ed-115">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="c75ed-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c75ed-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c75ed-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c75ed-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="c75ed-117">See also</span></span>

- [<span data-ttu-id="c75ed-118">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="c75ed-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
