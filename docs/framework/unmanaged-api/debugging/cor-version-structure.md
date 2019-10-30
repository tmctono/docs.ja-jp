---
title: COR_VERSION 構造体
ms.date: 03/30/2017
api_name:
- COR_VERSION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_VERSION
helpviewer_keywords:
- COR_VERSION structure [.NET Framework debugging]
ms.assetid: 5efaee1c-a001-4c73-9525-4160f4c71567
topic_type:
- apiref
ms.openlocfilehash: cc9a67e16635209c3bf303e97dc3e5938943a653
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099088"
---
# <a name="cor_version-structure"></a><span data-ttu-id="39ec1-102">COR_VERSION 構造体</span><span class="sxs-lookup"><span data-stu-id="39ec1-102">COR_VERSION Structure</span></span>
<span data-ttu-id="39ec1-103">共通言語ランタイムの標準の 4 つの部分のバージョン番号を保存します。</span><span class="sxs-lookup"><span data-stu-id="39ec1-103">Stores the standard four-part version number of the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39ec1-104">構文</span><span class="sxs-lookup"><span data-stu-id="39ec1-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_VERSION {  
    DWORD dwMajor;  
    DWORD dwMinor;  
    DWORD dwBuild;  
    DWORD dwSubBuild;  
} COR_VERSION;  
```  
  
## <a name="members"></a><span data-ttu-id="39ec1-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="39ec1-105">Members</span></span>  
  
|<span data-ttu-id="39ec1-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="39ec1-106">Member</span></span>|<span data-ttu-id="39ec1-107">説明</span><span class="sxs-lookup"><span data-stu-id="39ec1-107">Description</span></span>|  
|------------|-----------------|  
|`dwMajor`|<span data-ttu-id="39ec1-108">メジャー バージョン番号。</span><span class="sxs-lookup"><span data-stu-id="39ec1-108">The major version number.</span></span>|  
|`dwMinor`|<span data-ttu-id="39ec1-109">マイナー バージョン番号。</span><span class="sxs-lookup"><span data-stu-id="39ec1-109">The minor version number.</span></span>|  
|`dwBuild`|<span data-ttu-id="39ec1-110">ビルド番号。</span><span class="sxs-lookup"><span data-stu-id="39ec1-110">The build number.</span></span>|  
|`dwSubBuild`|<span data-ttu-id="39ec1-111">サブビルド番号。</span><span class="sxs-lookup"><span data-stu-id="39ec1-111">The sub-build number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39ec1-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="39ec1-112">Remarks</span></span>  
 <span data-ttu-id="39ec1-113">バージョン番号が1.0.3705.288 の場合、1はメジャーバージョン番号、0はマイナーバージョン番号、3705はビルド番号、288はサブビルド番号です。</span><span class="sxs-lookup"><span data-stu-id="39ec1-113">If the version number is 1.0.3705.288, 1 is the major version number, 0 is the minor version number, 3705 is the build number, and 288 is the sub-build number.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39ec1-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="39ec1-114">Requirements</span></span>  
 <span data-ttu-id="39ec1-115">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39ec1-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39ec1-116">**ヘッダー:** CorDebug .idl</span><span class="sxs-lookup"><span data-stu-id="39ec1-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="39ec1-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39ec1-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39ec1-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39ec1-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39ec1-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="39ec1-119">See also</span></span>

- [<span data-ttu-id="39ec1-120">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="39ec1-120">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="39ec1-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="39ec1-121">Debugging</span></span>](index.md)
