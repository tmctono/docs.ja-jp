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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61965841"
---
# <a name="createcoreclrdebugtarget-function"></a><span data-ttu-id="3b1bd-102">CreateCoreClrDebugTarget 関数</span><span class="sxs-lookup"><span data-stu-id="3b1bd-102">CreateCoreClrDebugTarget Function</span></span>
<span data-ttu-id="3b1bd-103">リモート コンピューターで実行されてを返すデバッガー プロキシへの接続を作成し、 [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)クエリ実行中のプロセスと読み込まれたランタイムに対するリモート コンピューター上に使用できるオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3b1bd-103">Creates a connection to a debugger proxy that is running on a remote machine, and returns an [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) object that can be used to query running processes and loaded runtimes on the remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b1bd-104">構文</span><span class="sxs-lookup"><span data-stu-id="3b1bd-104">Syntax</span></span>  
  
```  
HRESULT CreateCoreClrDebugTarget (  
       [in]  DWORD    dwAddress,   
       [out] ICoreClrDebugTarget**     ppTarget  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b1bd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3b1bd-105">Parameters</span></span>  
 `dwAddress`  
 <span data-ttu-id="3b1bd-106">[in] リモート対象コンピューターの IPv4 アドレス。</span><span class="sxs-lookup"><span data-stu-id="3b1bd-106">[in] IPv4 address of a remote target machine.</span></span>  
  
 `ppTarget`  
 <span data-ttu-id="3b1bd-107">[out]ポインターへのポインター、 [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)作成されるオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3b1bd-107">[out] Pointer to a pointer to an [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) object that will be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3b1bd-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="3b1bd-108">Return Value</span></span>  
 <span data-ttu-id="3b1bd-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="3b1bd-109">S_OK</span></span>  
 <span data-ttu-id="3b1bd-110">プロセス内の CLR 数が正常に判別され、対応するハンドルとパスの配列が正しく入力されました。</span><span class="sxs-lookup"><span data-stu-id="3b1bd-110">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="3b1bd-111">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="3b1bd-111">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="3b1bd-112">`ppTarget`  用に十分なメモリを割り当てることができません。</span><span class="sxs-lookup"><span data-stu-id="3b1bd-112">Unable to allocate enough memory for `ppTarget`.</span></span>  
  
 <span data-ttu-id="3b1bd-113">E_FAIL (またはその他の E_ リターン コード)</span><span class="sxs-lookup"><span data-stu-id="3b1bd-113">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="3b1bd-114">その他のエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="3b1bd-114">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b1bd-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="3b1bd-115">Requirements</span></span>  
 <span data-ttu-id="3b1bd-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b1bd-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b1bd-117">**ヘッダー:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="3b1bd-117">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="3b1bd-118">**ライブラリ:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="3b1bd-118">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="3b1bd-119">**.NET framework のバージョン:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="3b1bd-119">**.NET Framework Versions:** 3.5 SP1</span></span>
