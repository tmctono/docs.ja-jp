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
ms.openlocfilehash: 9d505b917c343c40c7fa2a7aecf3466578ae0a8d
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2020
ms.locfileid: "75936637"
---
# <a name="runtime_info_flags-enumeration"></a><span data-ttu-id="171cb-102">RUNTIME_INFO_FLAGS 列挙型</span><span class="sxs-lookup"><span data-stu-id="171cb-102">RUNTIME_INFO_FLAGS Enumeration</span></span>
<span data-ttu-id="171cb-103">共通言語ランタイム (CLR) に関する情報を返す必要があるかどうかを示す値を格納します。</span><span class="sxs-lookup"><span data-stu-id="171cb-103">Contains values that indicate what information about the common language runtime (CLR) should be returned.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="171cb-104">構文</span><span class="sxs-lookup"><span data-stu-id="171cb-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="171cb-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="171cb-105">Members</span></span>  
  
|<span data-ttu-id="171cb-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="171cb-106">Member</span></span>|<span data-ttu-id="171cb-107">説明</span><span class="sxs-lookup"><span data-stu-id="171cb-107">Description</span></span>|  
|------------|-----------------|  
|`RUNTIME_INFO_DONT_RETURN_DIRECTORY`|<span data-ttu-id="171cb-108">ディレクトリ情報を含めないことを示します。</span><span class="sxs-lookup"><span data-stu-id="171cb-108">Indicates that directory information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_RETURN_VERSION`|<span data-ttu-id="171cb-109">バージョン情報を含めないことを示します。</span><span class="sxs-lookup"><span data-stu-id="171cb-109">Indicates that version information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG`|<span data-ttu-id="171cb-110">エラーが発生したときにエラーダイアログボックスを表示しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="171cb-110">Indicates that an error dialog box should not be shown upon failure.</span></span>|  
|`RUNTIME_INFO_IGNORE_ERROR_MODE`|<span data-ttu-id="171cb-111">SEM_FAILCRITICALERRORS フラグを使用して[SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode)関数を呼び出した場合の効果をオーバーライドする必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="171cb-111">Indicates that the effects of calling the [SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) function with the SEM_FAILCRITICALERRORS flag should be overridden.</span></span> <span data-ttu-id="171cb-112">つまり、エラーが発生すると、抑制されるのではなく、インストールのダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="171cb-112">That is, an installation dialog box should be shown upon failure, instead of being suppressed.</span></span>|  
|`RUNTIME_INFO_REQUEST_AMD64`|<span data-ttu-id="171cb-113">AMD-64 互換バージョンのランタイムに関する情報の要求を示します。</span><span class="sxs-lookup"><span data-stu-id="171cb-113">Indicates a request for information about an AMD-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_IA64`|<span data-ttu-id="171cb-114">IA-64 互換バージョンのランタイムに関する情報の要求を示します。</span><span class="sxs-lookup"><span data-stu-id="171cb-114">Indicates a request for information about an IA-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_X86`|<span data-ttu-id="171cb-115">ランタイムの x86 互換バージョンに関する情報の要求を示します。</span><span class="sxs-lookup"><span data-stu-id="171cb-115">Indicates a request for information about an x86-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_UPGRADE_VERSION`|<span data-ttu-id="171cb-116">バージョンのアップグレード情報を含める必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="171cb-116">Indicates that version upgrade information should be included.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="171cb-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="171cb-117">Remarks</span></span>  
 <span data-ttu-id="171cb-118">次のプラットフォームアーキテクチャフラグは一度に1つだけ指定でき、組み合わせることはできません。</span><span class="sxs-lookup"><span data-stu-id="171cb-118">The following platform architecture flags can be specified only one at a time and cannot be combined:</span></span>  
  
- <span data-ttu-id="171cb-119">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="171cb-119">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
- <span data-ttu-id="171cb-120">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="171cb-120">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
- <span data-ttu-id="171cb-121">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="171cb-121">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="171cb-122">要件</span><span class="sxs-lookup"><span data-stu-id="171cb-122">Requirements</span></span>  
 <span data-ttu-id="171cb-123">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="171cb-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="171cb-124">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="171cb-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="171cb-125">**ライブラリ:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="171cb-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="171cb-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="171cb-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="171cb-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="171cb-127">See also</span></span>

- [<span data-ttu-id="171cb-128">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="171cb-128">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
