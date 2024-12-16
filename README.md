package teste.lucasvegi.pokemongooffline.Controller;

import android.app.Activity;
import android.content.Intent;
import android.database.Cursor;
import android.graphics.BitmapFactory;
import android.os.Bundle;
import android.view.Gravity;
import android.view.View;
import android.widget.ImageView;
import android.widget.TextView;
import teste.lucasvegi.pokemongooffline.Model.Pokestop;
import teste.lucasvegi.pokemongooffline.R;
import teste.lucasvegi.pokemongooffline.Util.BancoDadosSingleton;
import teste.lucasvegi.pokemongooffline.Util.MyApp;

public class PokestopActivity extends Activity {
    private TextView placeName;
    }

  public void PegaOvo(View view) {
        Pegou = false;
        Date TempoAtual = Calendar.getInstance().getTime();

  InteracaoPokestop inter = ControladoraFachadaSingleton.getInstance().getUltimaInteracao(Pkstp);
            if(diffSec > 300){

  ControladoraFachadaSingleton.getInstance().interagePokestop(Pkstp, TempoAtual);
                Toast.makeText(this,"Pegou Ovo ", Toast.LENGTH_LONG).show();
              //Pega o ovo
                Pegou = true;
            }
            else
                Toast.makeText(this,"Espere mais "+ String.valueOf(300-diffSec) +" segundos",Toast.LENGTH_SHORT).show();
            else{
                Toast toastEspere = Toast.makeText(MyApp.getAppContext(),"Espere mais "+ String.valueOf(300-diffSec) +" segundos",Toast.LENGTH_SHORT);
                toastEspere.setGravity(Gravity.TOP | Gravity.CENTER_HORIZONTAL,0,0);
                toastEspere.show();
            }
        }
        if(Pegou)
            Toast.makeText(this,"Pegou Ovo ",Toast.LENGTH_LONG).show();
        if(Pegou) {
            Integer xp = ControladoraFachadaSingleton.getInstance().getXpEvento("pokestop");
            Integer ovos = ControladoraFachadaSingleton.getInstance().getOvos().size();
            if(ovos > 8){
                Toast toastInventario = Toast.makeText(MyApp.getAppContext(), "Inventário de ovos está cheio!", Toast.LENGTH_LONG);
                toastInventario.setGravity(Gravity.TOP | Gravity.CENTER_HORIZONTAL,0,0);
                toastInventario.show();
            }
            else{
                Toast toastOvo = Toast.makeText(MyApp.getAppContext(), "Pegou Ovo ", Toast.LENGTH_LONG);
                toastOvo.setGravity(Gravity.TOP | Gravity.CENTER_HORIZONTAL,0,0);
                toastOvo.show();
            }
        }
    }

}
