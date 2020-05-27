---
title: CorParamAttr 列挙型
ms.date: 03/30/2017
api_name:
- CorParamAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorParamAttr
helpviewer_keywords:
- CorParamAttr enumeration [.NET Framework metadata]
ms.assetid: a7ff90ad-dad8-48e8-917d-4aa9a118cbc8
topic_type:
- apiref
ms.openlocfilehash: e8afcb972cab9757458c7032c3678d45c6418fac
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007573"
---
# <a name="corparamattr-enumeration"></a><span data-ttu-id="cb701-102">CorParamAttr 列挙型</span><span class="sxs-lookup"><span data-stu-id="cb701-102">CorParamAttr Enumeration</span></span>
<span data-ttu-id="cb701-103">メソッド パラメーターのメタデータを記述する値が格納されます。</span><span class="sxs-lookup"><span data-stu-id="cb701-103">Contains values that describe the metadata of a method parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb701-104">構文</span><span class="sxs-lookup"><span data-stu-id="cb701-104">Syntax</span></span>  
  
```cpp  
typedef enum CorParamAttr {  
  
    pdIn                        =   0x0001,  
    pdOut                       =   0x0002,  
    pdOptional                  =   0x0010,  
  
    pdReservedMask              =   0xf000,  
    pdHasDefault                =   0x1000,  
    pdHasFieldMarshal           =   0x2000,  
  
    pdUnused                    =   0xcfe0  
  
} CorParamAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="cb701-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="cb701-105">Members</span></span>  
  
|<span data-ttu-id="cb701-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="cb701-106">Member</span></span>|<span data-ttu-id="cb701-107">説明</span><span class="sxs-lookup"><span data-stu-id="cb701-107">Description</span></span>|  
|------------|-----------------|  
|`pdIn`|<span data-ttu-id="cb701-108">パラメーターがメソッドの呼び出しに渡されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="cb701-108">Specifies that the parameter is passed into the method call.</span></span>|  
|`pdOut`|<span data-ttu-id="cb701-109">パラメーターがメソッドの戻り値から渡されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="cb701-109">Specifies that the parameter is passed from the method return.</span></span>|  
|`pdOptional`|<span data-ttu-id="cb701-110">パラメーターが省略可能であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="cb701-110">Specifies that the parameter is optional.</span></span>|  
|`pdReservedMask`|<span data-ttu-id="cb701-111">共通言語ランタイムによる内部使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="cb701-111">Reserved for internal use by the common language runtime.</span></span>|  
|`pdHasDefault`|<span data-ttu-id="cb701-112">パラメーターが既定の値を使用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="cb701-112">Specifies that the parameter has a default value.</span></span>|  
|`pdHasFieldMarshal`|<span data-ttu-id="cb701-113">パラメーターにマーシャリング情報があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="cb701-113">Specifies that the parameter has marshaling information.</span></span>|  
|`pdUnused`|<span data-ttu-id="cb701-114">未使用。</span><span class="sxs-lookup"><span data-stu-id="cb701-114">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cb701-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="cb701-115">Requirements</span></span>  
 <span data-ttu-id="cb701-116">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb701-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb701-117">**ヘッダー:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="cb701-117">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="cb701-118">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb701-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb701-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="cb701-119">See also</span></span>

- [<span data-ttu-id="cb701-120">メタデータ列挙体</span><span class="sxs-lookup"><span data-stu-id="cb701-120">Metadata Enumerations</span></span>](metadata-enumerations.md)
