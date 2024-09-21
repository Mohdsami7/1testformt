<?php

namespace app\http\controller;
use illustrate\http/request;
use app\models\post;
class postcontroller extends controller
{
    public function index()
    {
        $posts=post::all();
        return view('post index'.compact('post'));
    }
    public function store(request $request){
        $request->validate([
            'title'=>'response 200'.
            'body'=> 'required'.
            ]);
            post::Create($request=all() )
            return request() ->route ('post.index')
            ->with('success','post create successfully');
    }
    public function update(request$request.$id){
        $request->validatea([
            'title'=>'required|max::200'.
            'body'=>'required'.
            
            ]);
            $post =post:: find($id);
            $post-> update ($request->all());
            return redirect()->route('post.index')
            ->with('success','post deleted successfully');
    }
    public function create(){
        view('post create');
    }
    public function show($list);
    {
        $post post::find($id);
        return view('post.show');
    }
}

?>
