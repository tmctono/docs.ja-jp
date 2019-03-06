---
title: LPOVERLAPPED_COMPLETION_ROUTINE 関数ポインター
ms.date: 03/30/2017
api_name:
- LPOVERLAPPED_COMPLETION_ROUTINE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- LPOVERLAPPED_COMPLETION_ROUTINE
helpviewer_keywords:
- LPOVERLAPPED_COMPLETION_ROUTINE function pointer [.NET Framework hosting]
ms.assetid: 5fb645d9-b818-401c-8c2c-c30d86de58ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f957ff6949ea2335c6606eb112352a5180e2c1c8
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500318"
---
# <a name="lpoverlappedcompletionroutine-function-pointer"></a><span data-ttu-id="34e07-102">LPOVERLAPPED_COMPLETION_ROUTINE 関数ポインター</span><span class="sxs-lookup"><span data-stu-id="34e07-102">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>
<span data-ttu-id="34e07-103">デバイスに対する重複 I/O (非同期 I/O) が完了したときに、ホストに通知する関数を指します。</span><span class="sxs-lookup"><span data-stu-id="34e07-103">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 <span data-ttu-id="34e07-104">この関数のポインターが非推奨とされた、[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="34e07-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34e07-105">構文</span><span class="sxs-lookup"><span data-stu-id="34e07-105">Syntax</span></span>  
  
```  
typedef VOID (*LPOVERLAPPED_COMPLETION_ROUTINE) (  
    [in] DWORD  dwErrorCode,  
    [in] DWORD  dwNumberOfBytesTransfered,  
    [in] LPVOID lpOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34e07-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="34e07-106">Parameters</span></span>  
 `dwErrorCode`  
 <span data-ttu-id="34e07-107">[in]デバイスが閉じられていない場合、エラー コードである値それ以外の場合、この値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="34e07-107">[in] A value that is an error code if the device has been closed; otherwise, this value is zero.</span></span>  
  
 <span data-ttu-id="34e07-108">デバイスを閉じる、保留中のすべてのデバイスに I/O をすぐに完了するとします。</span><span class="sxs-lookup"><span data-stu-id="34e07-108">Closing a device causes all pending I/O to the device to be completed immediately.</span></span>  
  
 `dwNumberOfBytesTransfered`  
 <span data-ttu-id="34e07-109">[in]I/O 操作によって転送されたバイト数。</span><span class="sxs-lookup"><span data-stu-id="34e07-109">[in] The number of bytes transferred by the I/O operation.</span></span>  
  
 `lpOverlapped`  
 <span data-ttu-id="34e07-110">[in]I/O 要求を完了するために使用する情報を格納する構造体へのポインター。</span><span class="sxs-lookup"><span data-stu-id="34e07-110">[in] A pointer to a structure that contains information to be used to complete the I/O request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34e07-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="34e07-111">Remarks</span></span>  
 <span data-ttu-id="34e07-112">関数`LPOVERLAPPED_COMPLETION_ROUTINE`ポイントはコールバック関数であり、ホスト アプリケーションの作成者によって実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34e07-112">The function to which `LPOVERLAPPED_COMPLETION_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="34e07-113">コールバック関数では、ホストが完了した I/O 要求を処理できるようにします。</span><span class="sxs-lookup"><span data-stu-id="34e07-113">The callback function allows the host to process the completed I/O request.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34e07-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="34e07-114">Requirements</span></span>  
 <span data-ttu-id="34e07-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="34e07-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34e07-116">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="34e07-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="34e07-117">**ライブラリ:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="34e07-117">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="34e07-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34e07-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34e07-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="34e07-119">See also</span></span>
- [<span data-ttu-id="34e07-120">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="34e07-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
