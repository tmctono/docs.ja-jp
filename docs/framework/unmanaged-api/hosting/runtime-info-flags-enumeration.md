---
title: RUNTIME_INFO_FLAGS 列挙型
ms.date: 03/30/2017
api_name:
- RUNTIME_INFO_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- RUNTIME_INFO_FLAGS
helpviewer_keywords:
- RUNTIME_INFO_FLAGS enumeration [.NET Framework hosting]
ms.assetid: adba37be-f775-4cdb-8919-5746ce694f33
topic_type:
- apiref
ms.openlocfilehash: da830aaaced179fed642340c33e7b7c37b350aa3
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006559"
---
# <a name="runtime_info_flags-enumeration"></a><span data-ttu-id="01f1e-102">RUNTIME_INFO_FLAGS 列挙型</span><span class="sxs-lookup"><span data-stu-id="01f1e-102">RUNTIME_INFO_FLAGS Enumeration</span></span>
<span data-ttu-id="01f1e-103">共通言語ランタイム (CLR) に関する情報を返す必要があるかどうかを示す値を格納します。</span><span class="sxs-lookup"><span data-stu-id="01f1e-103">Contains values that indicate what information about the common language runtime (CLR) should be returned.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01f1e-104">構文</span><span class="sxs-lookup"><span data-stu-id="01f1e-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
  
    RUNTIME_INFO_UPGRADE_VERSION             = 0x01,  
    RUNTIME_INFO_REQUEST_IA64                = 0x02,  
    RUNTIME_INFO_REQUEST_AMD64               = 0x04,  
    RUNTIME_INFO_REQUEST_X86                 = 0x08,  
    RUNTIME_INFO_DONT_RETURN_DIRECTORY       = 0x10,  
    RUNTIME_INFO_DONT_RETURN_VERSION         = 0x20,  
    RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG      = 0x40,  
    RUNTIME_INFO_IGNORE_ERROR_MODE           = 0x1000  
  
} RUNTIME_INFO_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="01f1e-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="01f1e-105">Members</span></span>  
  
|<span data-ttu-id="01f1e-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="01f1e-106">Member</span></span>|<span data-ttu-id="01f1e-107">説明</span><span class="sxs-lookup"><span data-stu-id="01f1e-107">Description</span></span>|  
|------------|-----------------|  
|`RUNTIME_INFO_DONT_RETURN_DIRECTORY`|<span data-ttu-id="01f1e-108">ディレクトリ情報を含めないことを示します。</span><span class="sxs-lookup"><span data-stu-id="01f1e-108">Indicates that directory information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_RETURN_VERSION`|<span data-ttu-id="01f1e-109">バージョン情報を含めないことを示します。</span><span class="sxs-lookup"><span data-stu-id="01f1e-109">Indicates that version information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG`|<span data-ttu-id="01f1e-110">エラーが発生したときにエラーダイアログボックスを表示しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="01f1e-110">Indicates that an error dialog box should not be shown upon failure.</span></span>|  
|`RUNTIME_INFO_IGNORE_ERROR_MODE`|<span data-ttu-id="01f1e-111">SEM_FAILCRITICALERRORS フラグを使用して[SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode)関数を呼び出した場合の効果をオーバーライドする必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="01f1e-111">Indicates that the effects of calling the [SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) function with the SEM_FAILCRITICALERRORS flag should be overridden.</span></span> <span data-ttu-id="01f1e-112">つまり、エラーが発生すると、抑制されるのではなく、インストールのダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="01f1e-112">That is, an installation dialog box should be shown upon failure, instead of being suppressed.</span></span>|  
|`RUNTIME_INFO_REQUEST_AMD64`|<span data-ttu-id="01f1e-113">AMD-64 互換バージョンのランタイムに関する情報の要求を示します。</span><span class="sxs-lookup"><span data-stu-id="01f1e-113">Indicates a request for information about an AMD-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_IA64`|<span data-ttu-id="01f1e-114">IA-64 互換バージョンのランタイムに関する情報の要求を示します。</span><span class="sxs-lookup"><span data-stu-id="01f1e-114">Indicates a request for information about an IA-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_X86`|<span data-ttu-id="01f1e-115">ランタイムの x86 互換バージョンに関する情報の要求を示します。</span><span class="sxs-lookup"><span data-stu-id="01f1e-115">Indicates a request for information about an x86-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_UPGRADE_VERSION`|<span data-ttu-id="01f1e-116">バージョンのアップグレード情報を含める必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="01f1e-116">Indicates that version upgrade information should be included.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01f1e-117">コメント</span><span class="sxs-lookup"><span data-stu-id="01f1e-117">Remarks</span></span>  
 <span data-ttu-id="01f1e-118">次のプラットフォームアーキテクチャフラグは一度に1つだけ指定でき、組み合わせることはできません。</span><span class="sxs-lookup"><span data-stu-id="01f1e-118">The following platform architecture flags can be specified only one at a time and cannot be combined:</span></span>  
  
- <span data-ttu-id="01f1e-119">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="01f1e-119">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
- <span data-ttu-id="01f1e-120">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="01f1e-120">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
- <span data-ttu-id="01f1e-121">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="01f1e-121">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01f1e-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="01f1e-122">Requirements</span></span>  
 <span data-ttu-id="01f1e-123">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01f1e-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01f1e-124">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="01f1e-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="01f1e-125">**ライブラリ:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="01f1e-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="01f1e-126">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01f1e-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01f1e-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="01f1e-127">See also</span></span>

- [<span data-ttu-id="01f1e-128">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="01f1e-128">Hosting Enumerations</span></span>](hosting-enumerations.md)
