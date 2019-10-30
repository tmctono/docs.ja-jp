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
ms.openlocfilehash: 103ac75e7c3eaf9739c3a448ff1c052c158621db
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73090902"
---
# <a name="lpoverlapped_completion_routine-function-pointer"></a><span data-ttu-id="b13d7-102">LPOVERLAPPED_COMPLETION_ROUTINE 関数ポインター</span><span class="sxs-lookup"><span data-stu-id="b13d7-102">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>
<span data-ttu-id="b13d7-103">デバイスに対する重複 I/O (非同期 I/O) が完了したときに、ホストに通知する関数を指します。</span><span class="sxs-lookup"><span data-stu-id="b13d7-103">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 <span data-ttu-id="b13d7-104">この関数ポインターは .NET Framework 4 で非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="b13d7-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b13d7-105">構文</span><span class="sxs-lookup"><span data-stu-id="b13d7-105">Syntax</span></span>  
  
```cpp  
typedef VOID (*LPOVERLAPPED_COMPLETION_ROUTINE) (  
    [in] DWORD  dwErrorCode,  
    [in] DWORD  dwNumberOfBytesTransfered,  
    [in] LPVOID lpOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b13d7-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b13d7-106">Parameters</span></span>  
 `dwErrorCode`  
 <span data-ttu-id="b13d7-107">からデバイスが閉じられている場合は、エラーコードである値。それ以外の場合、この値は0です。</span><span class="sxs-lookup"><span data-stu-id="b13d7-107">[in] A value that is an error code if the device has been closed; otherwise, this value is zero.</span></span>  
  
 <span data-ttu-id="b13d7-108">デバイスを閉じると、デバイスに対するすべての保留中の i/o が直ちに完了します。</span><span class="sxs-lookup"><span data-stu-id="b13d7-108">Closing a device causes all pending I/O to the device to be completed immediately.</span></span>  
  
 `dwNumberOfBytesTransfered`  
 <span data-ttu-id="b13d7-109">からI/o 操作によって転送されたバイト数。</span><span class="sxs-lookup"><span data-stu-id="b13d7-109">[in] The number of bytes transferred by the I/O operation.</span></span>  
  
 `lpOverlapped`  
 <span data-ttu-id="b13d7-110">からI/o 要求を完了するために使用される情報を格納する構造体へのポインター。</span><span class="sxs-lookup"><span data-stu-id="b13d7-110">[in] A pointer to a structure that contains information to be used to complete the I/O request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b13d7-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="b13d7-111">Remarks</span></span>  
 <span data-ttu-id="b13d7-112">`LPOVERLAPPED_COMPLETION_ROUTINE` ポイントする関数はコールバック関数であり、ホストアプリケーションのライターによって実装される必要があります。</span><span class="sxs-lookup"><span data-stu-id="b13d7-112">The function to which `LPOVERLAPPED_COMPLETION_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="b13d7-113">コールバック関数を使用すると、ホストは、完了した i/o 要求を処理できます。</span><span class="sxs-lookup"><span data-stu-id="b13d7-113">The callback function allows the host to process the completed I/O request.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b13d7-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="b13d7-114">Requirements</span></span>  
 <span data-ttu-id="b13d7-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b13d7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b13d7-116">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b13d7-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b13d7-117">**ライブラリ:** Mscorwks.dll</span><span class="sxs-lookup"><span data-stu-id="b13d7-117">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="b13d7-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b13d7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b13d7-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="b13d7-119">See also</span></span>

- [<span data-ttu-id="b13d7-120">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="b13d7-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
