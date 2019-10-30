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
ms.openlocfilehash: d52757f82a950c382c7c8f2162630eda7d7795e7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132090"
---
# <a name="createcoreclrdebugtarget-function"></a><span data-ttu-id="38291-102">CreateCoreClrDebugTarget 関数</span><span class="sxs-lookup"><span data-stu-id="38291-102">CreateCoreClrDebugTarget Function</span></span>
<span data-ttu-id="38291-103">リモートコンピューター上で実行されているデバッガープロキシへの接続を作成し、 [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)オブジェクトを返します。このオブジェクトを使用して、リモートコンピューター上で実行中のプロセスおよび読み込まれたランタイムのクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="38291-103">Creates a connection to a debugger proxy that is running on a remote machine, and returns an [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) object that can be used to query running processes and loaded runtimes on the remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38291-104">構文</span><span class="sxs-lookup"><span data-stu-id="38291-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateCoreClrDebugTarget (  
       [in]  DWORD    dwAddress,   
       [out] ICoreClrDebugTarget**     ppTarget  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38291-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="38291-105">Parameters</span></span>  
 `dwAddress`  
 <span data-ttu-id="38291-106">[in] リモート対象コンピューターの IPv4 アドレス。</span><span class="sxs-lookup"><span data-stu-id="38291-106">[in] IPv4 address of a remote target machine.</span></span>  
  
 `ppTarget`  
 <span data-ttu-id="38291-107">入出力作成される[ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)オブジェクトへのポインターへのポインター。</span><span class="sxs-lookup"><span data-stu-id="38291-107">[out] Pointer to a pointer to an [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) object that will be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="38291-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="38291-108">Return Value</span></span>  
 <span data-ttu-id="38291-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="38291-109">S_OK</span></span>  
 <span data-ttu-id="38291-110">プロセス内の CLR 数が正常に判別され、対応するハンドルとパスの配列が正しく入力されました。</span><span class="sxs-lookup"><span data-stu-id="38291-110">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="38291-111">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="38291-111">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="38291-112">`ppTarget`  用に十分なメモリを割り当てることができません。</span><span class="sxs-lookup"><span data-stu-id="38291-112">Unable to allocate enough memory for `ppTarget`.</span></span>  
  
 <span data-ttu-id="38291-113">E_FAIL (またはその他の E_ リターン コード)</span><span class="sxs-lookup"><span data-stu-id="38291-113">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="38291-114">その他のエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="38291-114">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38291-115">［要件］</span><span class="sxs-lookup"><span data-stu-id="38291-115">Requirements</span></span>  
 <span data-ttu-id="38291-116">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38291-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38291-117">**ヘッダー:** Coreclrremoteデバッグインターフェイス .h</span><span class="sxs-lookup"><span data-stu-id="38291-117">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="38291-118">**ライブラリ:** mscordbi_macx86</span><span class="sxs-lookup"><span data-stu-id="38291-118">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="38291-119">**.NET Framework のバージョン:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="38291-119">**.NET Framework Versions:** 3.5 SP1</span></span>
