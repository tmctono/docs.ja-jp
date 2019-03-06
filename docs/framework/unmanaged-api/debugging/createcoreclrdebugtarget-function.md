---
title: CreateCoreClrDebugTarget 関数
ms.date: 03/30/2017
api_name:
- CreateCorClrDebugTarget
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCoreClrDebugTarget
helpviewer_keywords:
- remote debugging API [Silverlight]
- Silverlight, remote debugging
- CreateCoreClrDebugTarget function
ms.assetid: 1cf4ca8e-d9bb-4633-9adf-5e24315bf87a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 48ce5381c745669b813f5b28d801add7daba7825
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470066"
---
# <a name="createcoreclrdebugtarget-function"></a><span data-ttu-id="ebe53-102">CreateCoreClrDebugTarget 関数</span><span class="sxs-lookup"><span data-stu-id="ebe53-102">CreateCoreClrDebugTarget Function</span></span>
<span data-ttu-id="ebe53-103">リモート コンピューターで実行されてを返すデバッガー プロキシへの接続を作成し、 [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)クエリ実行中のプロセスと読み込まれたランタイムに対するリモート コンピューター上に使用できるオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ebe53-103">Creates a connection to a debugger proxy that is running on a remote machine, and returns an [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) object that can be used to query running processes and loaded runtimes on the remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebe53-104">構文</span><span class="sxs-lookup"><span data-stu-id="ebe53-104">Syntax</span></span>  
  
```  
HRESULT CreateCoreClrDebugTarget (  
       [in]  DWORD    dwAddress,   
       [out] ICoreClrDebugTarget**     ppTarget  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ebe53-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ebe53-105">Parameters</span></span>  
 `dwAddress`  
 <span data-ttu-id="ebe53-106">[in] リモート対象コンピューターの IPv4 アドレス。</span><span class="sxs-lookup"><span data-stu-id="ebe53-106">[in] IPv4 address of a remote target machine.</span></span>  
  
 `ppTarget`  
 <span data-ttu-id="ebe53-107">[out]ポインターへのポインター、 [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)作成されるオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ebe53-107">[out] Pointer to a pointer to an [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) object that will be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ebe53-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="ebe53-108">Return Value</span></span>  
 <span data-ttu-id="ebe53-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="ebe53-109">S_OK</span></span>  
 <span data-ttu-id="ebe53-110">プロセス内の CLR 数が正常に判別され、対応するハンドルとパスの配列が正しく入力されました。</span><span class="sxs-lookup"><span data-stu-id="ebe53-110">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="ebe53-111">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="ebe53-111">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="ebe53-112">`ppTarget`  用に十分なメモリを割り当てることができません。</span><span class="sxs-lookup"><span data-stu-id="ebe53-112">Unable to allocate enough memory for `ppTarget`.</span></span>  
  
 <span data-ttu-id="ebe53-113">E_FAIL (またはその他の E_ リターン コード)</span><span class="sxs-lookup"><span data-stu-id="ebe53-113">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="ebe53-114">その他のエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="ebe53-114">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebe53-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="ebe53-115">Requirements</span></span>  
 <span data-ttu-id="ebe53-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebe53-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebe53-117">**ヘッダー:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="ebe53-117">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="ebe53-118">**ライブラリ:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="ebe53-118">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="ebe53-119">**.NET framework のバージョン:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="ebe53-119">**.NET Framework Versions:** 3.5 SP1</span></span>
